---
title: 第 2 步：创建用于 Oracle E-business Suite 项目的应用程序定义文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2665afde-0337-4795-ab4c-6223d39fdf9c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad908429c8daccef990377c953fda334558440aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374568"
---
# <a name="step-2-create-an-application-definition-file-for-the-oracle-e-business-suite-artifacts"></a>第 2 步：创建用于 Oracle E-business Suite 项目的应用程序定义文件
![步骤 2，共 4 步](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **若要完成的时间：** 15 分钟  
  
 **目标：** Microsoft SharePoint Server 中的业务数据目录功能公开，并将业务线 (LOB) 应用程序中的数据合并到门户。 若要将此数据合并到您的门户网站，必须生成可以使用 Microsoft Office SharePoint Server 应用程序定义文件。  
  
 Microsoft Office SharePoint Server 2007 SDK 提供的 Business Data Catalog Definition Editor 工具，可为业务数据目录中创建应用程序定义文件。 此工具自动生成 XML 文件，以便定义文件中，因此不需要手动创建该文件在 XML 编辑器。  
  
 要创建的 Microsoft Office SharePoint Server 应用程序的目的是：  
  
- 使用业务数据列表 Web 部件 MS_SAMPLE_EMPLOYEE 接口表中员工的查询基于一个雇员的姓名。  
  
- MS_SAMPLE_EMPLOYEE 接口表上，从 Microsoft Office SharePoint Server 中执行全文搜索。  
  
  对于每个这些要求，必须完成一组 Business Data Catalog Definition Editor tool 中的任务。 本主题提供有关如何执行这些任务的说明。  
  
## <a name="prerequisites"></a>先决条件  
  
-   必须确保您具有 Microsoft Office SharePoint Server 2007 SDK 的一部分安装 Business Data Catalog Definition Editor。 你可以下载从 SDK [ http://go.microsoft.com/fwlink/?LinkId=104130 ](http://go.microsoft.com/fwlink/?LinkId=104130)。  
  
-   发布 WCF 服务，如中所述[步骤 1:使用 Oracle E-business 适配器创建和发布 WCF 服务](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)。  
  

  
##  <a name="Connect"></a> 连接到 WCF LOB 服务并创建实体  
 您必须连接到 WCF 服务以提取 Web 服务描述语言 (WSDL) 服务。 从 WSDL，Business Data Catalog Definition Editor 提取方法。 这些方法可以用于创建实体。 对于本教程中，创建一个实体。  
  
#### <a name="to-connect-to-the-wcf-service-and-create-entities"></a>若要连接到 WCF 服务并创建实体  
  
1.  启动 Business Data Catalog Definition Editor。 上**启动**菜单上，单击**Microsoft Business Data Catalog Definition Editor**。  
  
2.  在工具栏上，单击**添加 LOB 系统**。  
  
3.  在添加 LOB 系统窗口中，单击**连接到 web 服务**。  
  
4.  在中**URL**框中，键入 WCF 服务的 URL。 对于本教程中，URL 将为：  
  
    ```  
    https://<COMPUTER_NAME>:<PORT_NUMBER>/MS_SAMPLE_EMPLOYEE/InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE.svc  
    ```  
  
     测试是否成功，如中所述发布 WCF 服务时，URL 是可用[步骤 1:使用 Oracle E-business 适配器创建和发布 WCF 服务](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)。  
  
5.  单击 **“连接”**。  
  
6.  若要查看你在 WCF 适配器服务开发向导中选择的操作，请单击**添加 Web 方法**选项卡。你将看到以下方法：**选择**。  
  
7.  拖动**选择**方法添加到设计图面。 将拖到设计图面上的方法，如创建实体，和该方法将成为该实体的一部分。  
  
     ![将 Select 方法添加到设计图面](../../adapters-and-accelerators/adapter-oracle-ebs/media/05-add-lob-system.gif "05_Add_LOB_System")  
  
8.  单击“确定” 。  
  
9. 在中**输入 LOB 系统的名称**对话框中键入名称**LOB 系统名称**框。 此示例中，称之为**MS_SAMPLE_EMPLOYEE**，然后单击**确定**。  
  
10. 在 Business Data Catalog Definition Editor，新创建的实体被列为**Entity0**。 重命名为实体**员工**。 执行以下步骤以重命名实体：  
  
    1.  展开**MS_SAMPLE_EMPLOYEE**节点，然后展开**实体**节点。  
  
    2.  选择**Entity0**节点。  
  
    3.  在属性窗格中，键入**员工**中**名称**框。  
  
         ![重命名实体](../../adapters-and-accelerators/adapter-oracle-ebs/media/06-entity-name.gif "06_Entity_Name")  
  
##  <a name="Headers"></a> 为方法中指定用户名和密码标头  
 如果创建 Oracle E-business Suite MS_SAMPLE_EMPLOYEE 接口表上的选择操作的 WCF 服务，请指定用户名称和密码标头中的终结点行为配置的一部分[步骤 1:使用 Oracle E-business 适配器创建和发布 WCF 服务](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)。 必须指定 Select 方法属性相同的值。  
  
#### <a name="to-specify-user-name-and-password-headers-for-the-select-method"></a>若要指定用户名称和密码标头的 Select 方法  
  
1.  在元数据对象窗格中，展开**员工**节点，然后展开**方法**节点。  
  
2.  单击**选择**节点，并在属性窗格中单击省略号 （...） 按钮根据**属性**框。  
  
3.  在 PropertyView 集合编辑器窗口中，单击**外**，然后在属性窗格中，键入**HttpHeaderUserName**有关**名称**框。 类型**MyUserHeader**有关**PropertyValue**框。 选择**System.String**有关**类型**框。  
  
4.  在 PropertyView 集合编辑器窗口中，单击**外**，然后在属性窗格中，键入**HttpHeaderPassword**有关**名称**框。 同样，键入**MyPasswordHeader**有关**PropertyValue**框。 选择**System.String**有关**类型**框。  
  
     ![将属性添加](../../adapters-and-accelerators/adapter-oracle-ebs/media/07-propertviewcollection-editor.gif "07_PropertViewCollection_Editor")  
  
5.  单击“确定” 。  
  
##  <a name="Scenario1"></a> 方案 1:使用业务数据列表 Web 部件的员工的查询  
 若要创建可用于搜索业务数据列表 Web 部件的员工和基于雇员姓名的应用程序定义文件，必须执行以下一组任务。  
  
1.  在中**选择**方法，创建一个筛选器，并将其映射到**筛选器**参数。  
  
2.  创建**Finder**方法实例**选择**方法。 一个**Finder**方法检索基于筛选器记录的列表。  
  
#### <a name="to-create-a-filter-and-map-it-to-the-filter-parameter"></a>若要创建筛选器，并将其映射到筛选器参数  
  
1.  创建一个筛选器。  
  
    1.  在元数据对象窗格中，展开**员工**节点，然后展开**方法**节点。  
  
    2.  展开**选择**方法中，右键单击**筛选器**，然后单击**添加筛选器**。  
  
         ![向 SELECT 方法添加筛选器](../../adapters-and-accelerators/adapter-oracle-ebs/media/08-add-filter.gif "08_Add_Filter")  
  
    3.  在属性窗格中的**FilterType**属性中，选择**等于**。  
  
    4.  在属性窗格中，键入**EmployeeName**中**名称**框。  
  
         ![指定筛选器属性](../../adapters-and-accelerators/adapter-oracle-ebs/media/09-filter-properties.gif "09_Filter_Properties")  
  
2.  筛选器映射到**筛选器**中的参数**选择**方法。  
  
    1.  在元数据对象窗格中，展开**员工**节点，然后展开**方法**节点。  
  
    2.  展开**选择**方法，然后展开**参数**节点。  
  
    3.  展开**筛选器**节点，然后单击第二个**筛选器**节点。  
  
    4.  在属性窗格中选择**EmployeeName**从**FilterDescriptor**列表。  
  
         ![将筛选器映射到 Select 方法参数](../../adapters-and-accelerators/adapter-oracle-ebs/media/10-map-filter.gif "10_Map_Filter")  
  
#### <a name="to-create-a-finder-method-instance-for-the-select-method"></a>若要创建 Select 方法的 Finder 方法实例  
  
1.  在元数据对象窗格中，展开**员工**节点，然后展开**方法**节点。  
  
2.  展开**选择**节点，右键单击**实例**，然后单击**添加方法实例**。  
  
     ![添加方法实例](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")  
  
3.  在创建方法实例窗口中，单击**Finder**有关**方法实例类型**。 选择**返回**有关**的返回 TypeDescriptor**。  
  
     ![创建 Finder 方法实例](../../adapters-and-accelerators/adapter-oracle-ebs/media/12-create-method-instance.gif "12_Create_Method_Instance")  
  
4.  单击“确定” 。  
  
5.  在属性窗格中，键入**Finder_Instance**中**名称**框。  
  
     ![指定 Finder 方法实例的名称](../../adapters-and-accelerators/adapter-oracle-ebs/media/13-instance-property.gif "13_Instance_Property")  
  
##  <a name="Scenario2"></a> 方案 2:从 Microsoft Office SharePoint Server MS_SAMPLE_EMPLOYEE 接口表的全文搜索  
 若要创建可用于从 Microsoft Office SharePoint Server MS_SAMPLE_EMPLOYEE 接口表中执行全文搜索应用程序定义文件，必须执行以下一组任务。  
  
-   在中**选择**方法中，创建一个标识符，并将其映射到筛选器参数和返回值，用于存储员工姓名。  
  
-   创建**特定的 Finder**方法实例**选择**。 **特定的 Finder**方法将查找特定记录基于标识符，即，一个雇员的姓名。  
  
-   创建 ID 枚举器方法实例。  
  
#### <a name="to-create-an-identifier-and-map-it-to-the-filter-parameter-and-employee-name-return-value"></a>若要创建一个标识符，并将其映射到筛选器参数和员工名称返回值  
  
1.  创建标识符**员工**实体。  
  
    1.  在元数据对象窗格中，展开**员工**节点。  
  
    2.  右键单击**标识符**节点，并选择**添加标识符**。  
  
         ![创建标识符](../../adapters-and-accelerators/adapter-oracle-ebs/media/14-create-identifier.gif "14_Create_Identifier")  
  
    3.  在属性窗格中，键入**EmployeeName**中**名称**框。  
  
    4.  选择**System.String**有关**类型**框。  
  
         ![指定标识符属性](../../adapters-and-accelerators/adapter-oracle-ebs/media/15-identifier-properties.gif "15_Identifier_Properties")  
  
2.  将标识符映射到的筛选器参数**选择**方法。  
  
    1.  在元数据对象窗格中，展开**员工**节点，然后展开**方法**节点。  
  
    2.  展开**选择**方法，然后展开**参数**节点。  
  
    3.  展开**筛选器**参数，然后单击第二个**筛选器**节点。  
  
    4.  在属性窗格中选择**EmployeeName [Employee]** 从**标识符**列表。  
  
         ![设置筛选器参数的标识符](../../adapters-and-accelerators/adapter-oracle-ebs/media/16-set-identifier.gif "16_Set_Identifier")  
  
3.  将标识符映射到员工名称返回值。  
  
    1.  在元数据对象窗格中，展开**员工**节点，然后展开**方法**节点。  
  
    2.  展开**选择**方法，然后展开**参数**节点。  
  
    3.  展开**返回**节点，然后第二个**返回**节点，然后**项**节点，并单击**名称**节点。  
  
    4.  在属性窗格中选择**EmployeeName [Employee]** 从**标识符**列表。  
  
#### <a name="to-create-a-specific-finder-method-instance-for-the-select-method"></a>若要创建 Select 方法的特定的 Finder 方法实例  
  
1.  在元数据对象窗格中，展开**员工**节点，然后**方法**节点。  
  
2.  展开**选择**节点，右键单击**实例**，然后选择**添加方法实例**以打开创建方法实例窗口。  
  
     ![添加方法实例](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")  
  
3.  在创建方法实例窗口中，选择**特定的 Finder**有关**方法实例类型**。 选择**返回**有关**的返回 TypeDescriptor**。  
  
     ![添加特定的 Finder 方法实例](../../adapters-and-accelerators/adapter-oracle-ebs/media/17-specific-finder.gif "17_Specific_Finder")  
  
4.  单击“确定” 。  
  
5.  在属性窗格中，键入**SpeciFinder_Instance**有关**名称**框。  
  
#### <a name="to-create-an-id-enumerator-method-instance-for-the-select-method"></a>若要创建 Id 枚举器方法实例的 Select 方法  
  
1.  在元数据对象窗格中，展开**员工**节点，然后**方法**节点。  
  
2.  展开**选择**节点，右键单击**实例**，然后选择**添加方法实例**以打开创建方法实例窗口。  
  
     ![添加方法实例](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")  
  
3.  在创建方法实例窗口中，选择**Id 枚举器**有关**方法实例类型**。 选择**返回**有关**的返回 TypeDescriptor**。  
  
     ![创建 Id 枚举器方法实例](../../adapters-and-accelerators/adapter-oracle-ebs/media/18-id-enumerator.gif "18_ID_Enumerator")  
  
4.  单击“确定” 。  
  
5.  在属性窗格中，键入**IDEnumerator_Instance**有关**名称**框。  
  
##  <a name="Defaults"></a> 设置方法实例的默认参数  
 Select 方法要求您指定的列名称。 因此，您需要指定的默认值**COLUMN_NAMES**前面创建的查找器、 特定的 Finder 和 Id 枚举器方法实例的参数。 此外，还应指定默认值为**筛选器**Id 枚举器方法实例的参数。  
  
#### <a name="to-set-the-default-parameters-for-the-method-instances"></a>若要设置的方法实例的默认参数  
  
1.  在元数据对象窗格中，展开**员工**节点，然后展开**方法**节点。  
  
2.  展开**选择**节点，然后展开**参数**节点。  
  
3.  展开**COLUMN_NAMES**节点，并选择**COLUMN_NAMES**参数。  
  
4.  在属性窗格中，单击省略号按钮 （...） 针对**DefaultValues**框。  
  
5.  在中**DefaultValueView 集合编辑器**对话框中，单击**添加**，然后在属性窗格中，单击**Finder_Instance**中**SelectMethodInstance**列表。  
  
     ![指定 Finder 实例的默认值](../../adapters-and-accelerators/adapter-oracle-ebs/media/19-finderinstance-defaults.gif "19_FinderInstance_Defaults")  
  
6.  类型`*`中**值**框。  
  
7.  同样，重复步骤 5 和 6 中添加的默认值**SpecificFinder_Instance**并**IDEnumerator_Instance**方法实例。  
  
8.  在中**DefaultValueView 集合编辑器**对话框中，单击**确定**。  
  
9. 接下来，添加的默认值**筛选器**参数**IDEnumerator_Instance**方法实例。 展开**筛选器**节点，并选择**筛选器**参数。  
  
10. 在属性窗格中，单击省略号按钮 （...） 针对**DefaultValues**框。  
  
11. 在中**DefaultValueView 集合编辑器**对话框中，单击**添加**，然后在属性窗格中，单击**IDEnumerator_Instance**中**SelectMethodInstance**列表。  
  
12. 类型`%`中**值**框。  
  
     ![Id 枚举器实例的默认值](../../adapters-and-accelerators/adapter-oracle-ebs/media/20-idenumeratorinstance-defaults.gif "20_IDEnumeratorInstance_Defaults")  
  
13. 在中**DefaultValueView 集合编辑器**对话框中，单击**确定**。  
  
##  <a name="SSO"></a> 连接到 Oracle E-business Suite 中设置了单一登录  
 执行本主题中的所有过程完成后，您将创建可导入 SharePoint 应用程序的应用程序定义文件。 从应用程序，您调用的方法来从 Oracle E-business Suite 中检索相关数据。 若要启用此功能，必须在 SharePoint 应用程序中创建 Oracle E-business Suite 中的用户和用户之间的映射。 在导入应用程序定义文件后，可以在 SharePoint 中心管理控制台中创建此映射。  
  
 但是，若要创建该映射必须设置属性**SecondarySsoApplicationId**中 Business Data Catalog Definition Editor。  
  
#### <a name="to-set-the-secondaryssoapplicationid-property"></a>若要设置 SecondarySsoApplicationId 属性  
  
1.  在元数据对象窗格中，展开**MS_SAMPLE_EMPLOYEE**节点，然后展开**实例**节点。  
  
2.  单击**MS_SAMPLE_EMPLOYEE_Instance**，并在属性窗格中，单击省略号 （...） 按钮针对**属性**框。  
  
3.  在中**PropertyView 集合编辑器**对话框中，单击**添加**，然后在属性窗格中，键入**SecondarySsoApplicationId**为**名称**框。 同样，键入**OracleSSO**有关**PropertyValue**框。 选择**System.String**有关**类型**框。  
  
     ![添加 SSO 属性](../../adapters-and-accelerators/adapter-oracle-ebs/media/21-sso.gif "21_SSO")  
  
4.  单击“确定” 。  
  
##  <a name="Export"></a> 应用程序定义导出到文件  
 现在已创建包含 Oracle E-business Suite 实例元数据的应用程序定义。 必须将此定义导出到 XML 文件，可以导入到 Microsoft Office SharePoint Server。  
  
#### <a name="to-export-the-application-definition-to-a-file"></a>若要将应用程序定义导出到文件  
  
1.  在元数据对象窗格中，右键单击**MS_SAMPLE_EMPLOYEE**节点，并单击**导出**。  
  
2.  将文件另存 Employee.xml。  
  
## <a name="next-steps"></a>后续步骤  
 现在必须创建 SharePoint 应用程序以从 Oracle E-business Suite 中检索数据。 有关说明，请参阅[步骤 3:创建 SharePoint 应用程序以从 Oracle E-business Suite 中检索数据](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)。  
  
## <a name="see-also"></a>请参阅  
 [教程：从 SharePoint 站点上的 Oracle E-business Suite 中显示数据](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)