---
title: Hantera uppgifter i en organisationshierarki med hjälp av hanterarvyn
seo-title: Managing tasks in an organizational hierarchy using Manager View
description: Hur chefer och organisationschefer kan komma åt och arbeta med uppgifter i sina direkta och indirekta rapporter på fliken Att göra på arbetsytan i AEM Forms.
seo-description: How managers and organization heads can access and work on the tasks of their direct and indirect reports in the To-do tab in AEM Forms workspace.
uuid: a44d5a64-c03a-4337-8577-b121e6202449
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: c7cf28bf-2806-47bc-a803-8bc0e803fc4d
exl-id: 28877528-2f91-4ee0-b9d8-c7df364ed803
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 0%

---

# Hantera uppgifter i en organisationshierarki med hjälp av hanterarvyn {#managing-tasks-in-an-organizational-hierarchy-using-manager-view}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

På AEM Forms arbetsyta kan chefer nu komma åt uppgifter som tilldelats alla i deras hierarki - direkta eller indirekta rapporter - och utföra olika åtgärder på dem. Uppgifterna är tillgängliga på fliken Att göra på arbetsytan i AEM Forms. De åtgärder som stöds för de direkta rapporterna är:

**Framåt** Vidarebefordra en uppgift från en direkt rapport till valfri användare.

**Anspråk** Gör anspråk på en uppgift som en direkt rapport.

**Anspråk och öppna** Gör anspråk på en uppgift i en direkt rapport och öppna den automatiskt i listan Att göra i hanteraren.

**Avvisa** Avvisa en uppgift som har vidarebefordrats till en direkt rapport av en annan användare. Det här alternativet är tillgängligt för uppgifter som vidarebefordras av andra användare till en direkt rapport.

AEM Forms begränsar en användares åtkomst till endast de uppgifter som användaren har åtkomstkontroll för. En sådan kontroll säkerställer att en användare bara kan hämta de uppgifter som användaren har åtkomstbehörighet för. Med hjälp av webbtjänster och implementeringar från tredje part för att definiera hierarkin kan en organisation anpassa definitionen av chef och dirigera rapporter efter deras behov.

1. Skapa en DSC. Mer information finns i avsnittet om att utveckla komponenter för AEM Forms i [Programmera med AEM Forms](https://www.adobe.com/go/learn_aemforms_programming_63) guide.
1. I DSC definierar du en ny SPI för hierarkihantering för att definiera direkta rapporter och hierarkier inom AEM Forms-användarna. Här följer ett exempel på Java™-kodfragment.

   ```as3
   public class MyHierarchyMgmtService 
   { 
        /*
       Input : Principal Oid for a livecycle user
       Output : Returns true when the user is either the service invoker OR his direct/indirect report.
       */
       boolean isInHierarchy(String principalOid) {
   
       }
   
       /* 
       Input : Principal Oid for a livecycle user
       Output : List of principal Oids for direct reports of the livecycle user
       A user may get direct reports only for himself OR his direct/indirect reports.
       So the API is functionally equivalent to - 
       isInHierarchy(principalOid) ? <return direct reports> : <return empty list>
       */
       List<String> getDirectReports(String principalOid) {
   
       }
   
       /* 
       Returns whether a livecycle user has direct reports or not.
       It's functionally equivalent to -
       getDirectReports(principalOid).size()>0
       */
       boolean isManager(String principalOid) {
   
       }  
   }
   ```

1. Skapa en component.xml-fil. Kontrollera att spec-id måste vara samma som i kodutdraget nedan. Här följer ett exempel på ett kodfragment som du kan återanvända.

   ```as3
   <component xmlns="https://adobe.com/idp/dsc/component/document"> 
       <component-id>com.adobe.sample.SampleDSC</component-id> 
       <version>1.1</version> 
       <supports-export>false</supports-export> 
         <descriptor-class>com.adobe.idp.dsc.component.impl.DefaultPOJODescriptorImpl</descriptor-class> 
         <services> 
           <service name="MyHierarchyMgmtService" title="My hierarchy management service" orchestrateable="false"> 
           <auto-deploy service-id="MyHierarchyMgmtService" category-id="Sample DSC" major-version="1" minor-version="0" /> 
           <description>Service for resolving hierarchy management.</description> 
            <specifications> 
            <specification spec-id="com.adobe.idp.taskmanager.dsc.enterprise.HierarchyManagementProvider"/> 
            </specifications> 
           <specification-version>1.0</specification-version> 
           <implementation-class>com.adobe.sample.hierarchymanagement.MyHierarchyMgmtService</implementation-class> 
           <request-processing-strategy>single_instance</request-processing-strategy> 
           <supported-connectors>default</supported-connectors> 
           <operation-config> 
               <operation-name>*</operation-name> 
               <transaction-type>Container</transaction-type> 
               <transaction-propagation>supports</transaction-propagation> 
               <!--transaction-timeout>3000</transaction-timeout--> 
           </operation-config> 
           <operations> 
               <operation anonymous-access="true" name="isInHierarchy" method="isInHierarchy"> 
                   <input-parameter name="principalOid" type="java.lang.String" /> 
                   <output-parameter name="result" type="java.lang.Boolean"/> 
               </operation> 
               <operation anonymous-access="true" name="getDirectReports" method="getDirectReports"> 
                   <input-parameter name="principalOid" type="java.lang.String" /> 
                   <output-parameter name="result" type="java.util.List"/> 
               </operation> 
               <operation anonymous-access="true" name="isManager" method="isManager"> 
                   <input-parameter name="principalOid" type="java.lang.String" /> 
                   <output-parameter name="result" type="java.lang.Boolean"/> 
               </operation> 
               </operations> 
               </service> 
         </services>
   </component>
   ```

1. Distribuera DSC via Workbench. Starta om `ProcessManagementTeamTasksService` service.
1. Du kan behöva uppdatera webbläsaren eller logga ut/logga in med användaren igen.

Följande skärm visar hur du får åtkomst till uppgifter i direkta rapporter och tillgängliga åtgärder.

![cu_manager_view](assets/cu_manager_view.png)

Få tillgång till uppgifter som hör till underställda och agera på dessa
