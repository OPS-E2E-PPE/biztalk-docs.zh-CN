---
title: 步骤 2： 创建 Oracle E-business Suite 项目的应用程序定义文件 |Microsoft 文档
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
ms.openlocfilehash: 4ed4340893d351d8406212b585e6216de19c634c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22219301"
---
# <a name="step-2-create-an-application-definition-file-for-the-oracle-e-business-suite-artifacts"></a>步骤 2： 创建 Oracle E-business Suite 项目的应用程序定义文件
![步骤 2 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **完成时间：** 15 分钟  
  
 **目标：** Microsoft SharePoint Server 中的业务数据目录功能公开，并将从-的业务线 (LOB) 应用程序的数据合并到门户。 若要将此数据合并到您的门户网站，必须在生成应用程序定义文件，可以使用 Microsoft Office SharePoint Server。  
  
 业务数据目录定义编辑器工具，适用于 Microsoft Office SharePoint Server 2007 SDK，可为业务数据目录中创建应用程序定义文件。 此工具自动生成一个 XML 文件定义文件中，因此不需要手动创建该文件在 XML 编辑器。  
  
 要创建 Microsoft Office SharePoint Server 应用程序的目的是：  
  
-   查询中使用业务数据列表 Web 部件 MS_SAMPLE_EMPLOYEE 接口表员工的基于雇员姓名。  
  
-   执行从 Microsoft Office SharePoint Server 上 MS_SAMPLE_EMPLOYEE 接口表的全文搜索。  
  
 对于每个这些要求，你必须完成一组在业务数据目录定义编辑器工具中的任务。 本主题提供有关如何执行这些任务的说明。  
  
## <a name="prerequisites"></a>先决条件  
  
-   请确保已安装 Microsoft Office SharePoint Server 2007 SDK 的一部分业务数据目录定义编辑器。 你可以下载 SDK 从[http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130)。  
  
-   将 WCF 服务发布中所述[步骤 1： 使用 Oracle E-business 适配器创建和发布 WCF 服务](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)。  
  

  
##  <a name="Connect"></a>连接到 WCF LOB 服务并创建实体  
 你必须连接到要提取 Web 服务描述语言 (WSDL) 服务的 WCF 服务。 从 WSDL，业务数据目录定义编辑器中提取方法。 这些方法可以用于创建实体。 对于本教程中，创建实体。  
  
#### <a name="to-connect-to-the-wcf-service-and-create-entities"></a>若要连接到 WCF 服务并创建实体  
  
1.  启动业务数据目录定义编辑器。 上**启动**菜单上，单击**Microsoft 业务数据目录定义编辑器**。  
  
2.  在工具栏上，单击**添加 LOB 系统**。  
  
3.  在添加 LOB 系统窗口中，单击**连接到 web 服务**。  
  
4.  在**URL**框中，键入 WCF 服务的 URL。 对于本教程，则 URL 将为：  
  
    ```  
    https://<COMPUTER_NAME>:<PORT_NUMBER>/MS_SAMPLE_EMPLOYEE/InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE.svc  
    ```  
  
     当你测试是否成功中, 所述发布 WCF 服务时，才可用 URL[步骤 1： 使用 Oracle E-business 适配器创建和发布 WCF 服务](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)。  
  
5.  单击 **“连接”**。  
  
6.  若要查看在 WCF 适配器服务开发向导中选择的操作，请单击**添加 Web 方法**选项卡。你将看到以下方法：**选择**。  
  
7.  拖动**选择**到设计图面上的方法。 将方法拖到设计图面中，创建实体时，和方法将成为该实体的一部分。  
  
     ![将选择的方法添加到设计图面](../../adapters-and-accelerators/adapter-oracle-ebs/media/05-add-lob-system.gif "05_Add_LOB_System")  
  
8.  单击 **“确定”**。  
  
9. 在**输入 LOB 系统的名称**对话框中，键入一个名称中**LOB 系统名称**框。 此示例中，称之为**MS_SAMPLE_EMPLOYEE**，然后单击**确定**。  
  
10. 在业务数据目录定义编辑器中，新创建的实体被列为**Entity0**。 重命名该实体，**员工**。 执行以下步骤以重命名实体：  
  
    1.  展开**MS_SAMPLE_EMPLOYEE**节点，然后展开**实体**节点。  
  
    2.  选择**Entity0**节点。  
  
    3.  在属性窗格中，键入**员工**中**名称**框。  
  
         ![重命名实体](../../adapters-and-accelerators/adapter-oracle-ebs/media/06-entity-name.gif "06_Entity_Name")  
  
##  <a name="Headers"></a>为方法中指定用户名和密码标头  
 如果创建 Oracle E-business Suite MS_SAMPLE_EMPLOYEE 接口表上的选择操作的 WCF 服务，请指定用户名称和密码标头中的终结点行为配置的一部分[步骤 1： 使用 Oracle创建和发布 WCF 服务的电子商务适配器](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)。 必须指定 Select 方法属性的相同值。  
  
#### <a name="to-specify-user-name-and-password-headers-for-the-select-method"></a>若要指定用户名称和密码标头的选择方法  
  
1.  在元数据对象窗格中，展开**员工**节点，然后展开**方法**节点。  
  
2.  单击**选择**节点，然后在属性窗格中单击针对省略号 （...） 按钮**属性**框。  
  
3.  在 PropertyView 集合编辑器窗口中，单击**添加**，然后在属性窗格中，键入**HttpHeaderUserName**为**名称**框。 类型**MyUserHeader**为**PropertyValue**框。 选择**System.String**为**类型**框。  
  
4.  在 PropertyView 集合编辑器窗口中，单击**添加**，然后在属性窗格中，键入**HttpHeaderPassword**为**名称**框。 同样，键入**MyPasswordHeader**为**PropertyValue**框。 选择**System.String**为**类型**框。  
  
     ![将属性添加](../../adapters-and-accelerators/adapter-oracle-ebs/media/07-propertviewcollection-editor.gif "07_PropertViewCollection_Editor")  
  
5.  单击 **“确定”**。  
  
##  <a name="Scenario1"></a>使用业务数据列表 Web 部件的员工的方案 1： 查询  
 若要创建可用于搜索业务数据列表 Web 部件的员工和基于员工名称的应用程序定义文件，必须执行以下一组任务。  
  
1.  在**选择**方法，创建筛选器，并将其映射到**筛选器**参数。  
  
2.  创建**Finder**方法实例**选择**方法。 A **Finder**方法检索基于筛选器的记录的列表。  
  
#### <a name="to-create-a-filter-and-map-it-to-the-filter-parameter"></a>创建筛选器，并将其映射到筛选器参数  
  
1.  创建筛选器。  
  
    1.  在元数据对象窗格中，展开**员工**节点，然后展开**方法**节点。  
  
    2.  展开**选择**方法中，右键单击**筛选器**，然后单击**添加筛选器**。  
  
         ![将筛选器添加到选择的方法](../../adapters-and-accelerators/adapter-oracle-ebs/media/08-add-filter.gif "08_Add_Filter")  
  
    3.  在属性窗格中，为**FilterType**属性中，选择**等于**。  
  
    4.  在属性窗格中，键入**员工姓名**中**名称**框。  
  
         ![指定筛选器属性](../../adapters-and-accelerators/adapter-oracle-ebs/media/09-filter-properties.gif "09_Filter_Properties")  
  
2.  映射到筛选器**筛选器**中的参数**选择**方法。  
  
    1.  在元数据对象窗格中，展开**员工**节点，然后展开**方法**节点。  
  
    2.  展开**选择**方法，然后展开**参数**节点。  
  
    3.  展开**筛选器**节点，然后单击第二个**筛选器**节点。  
  
    4.  在属性窗格中，选择**员工姓名**从**FilterDescriptor**列表。  
  
         ![映射到选择的方法参数的筛选器](../../adapters-and-accelerators/adapter-oracle-ebs/media/10-map-filter.gif "10_Map_Filter")  
  
#### <a name="to-create-a-finder-method-instance-for-the-select-method"></a>若要创建 Select 方法的 Finder 方法实例  
  
1.  在元数据对象窗格中，展开**员工**节点，然后展开**方法**节点。  
  
2.  展开**选择**节点，右键单击**实例**，然后单击**添加方法实例**。  
  
     ![添加方法实例](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")  
  
3.  在创建方法实例窗口中，单击**Finder**为**方法实例类型**。 选择**返回**为**返回 TypeDescriptor**。  
  
     ![创建 Finder 方法实例](../../adapters-and-accelerators/adapter-oracle-ebs/media/12-create-method-instance.gif "12_Create_Method_Instance")  
  
4.  单击 **“确定”**。  
  
5.  在属性窗格中，键入**Finder_Instance**中**名称**框。  
  
     ![指定的 Finder 方法实例的名称](../../adapters-and-accelerators/adapter-oracle-ebs/media/13-instance-property.gif "13_Instance_Property")  
  
##  <a name="Scenario2"></a>方案 2： 从 Microsoft Office SharePoint Server MS_SAMPLE_EMPLOYEE 接口表上的全文搜索  
 若要创建应用程序定义文件可以用于从 Microsoft Office SharePoint Server MS_SAMPLE_EMPLOYEE 接口表上执行全文搜索，必须执行以下一组任务。  
  
-   在**选择**方法，创建一个标识符，并将其映射到筛选器参数和返回值，用于存储员工姓名。  
  
-   创建**特定的 Finder**方法实例**选择**。 **特定的 Finder**方法将查找特定记录基于标识符，即雇员姓名。  
  
-   创建一个 ID 枚举数方法实例。  
  
#### <a name="to-create-an-identifier-and-map-it-to-the-filter-parameter-and-employee-name-return-value"></a>创建一个标识符，并将其映射到筛选器参数和员工名称返回值  
  
1.  创建的标识符**员工**实体。  
  
    1.  在元数据对象窗格中，展开**员工**节点。  
  
    2.  右键单击**标识符**节点，，然后选择**添加标识符**。  
  
         ![创建一个标识符](../../adapters-and-accelerators/adapter-oracle-ebs/media/14-create-identifier.gif "14_Create_Identifier")  
  
    3.  在属性窗格中，键入**员工姓名**中**名称**框。  
  
    4.  选择**System.String**为**类型**框。  
  
         ![指定标识符属性](../../adapters-and-accelerators/adapter-oracle-ebs/media/15-identifier-properties.gif "15_Identifier_Properties")  
  
2.  标识符映射到的筛选器参数**选择**方法。  
  
    1.  在元数据对象窗格中，展开**员工**节点，然后展开**方法**节点。  
  
    2.  展开**选择**方法，然后展开**参数**节点。  
  
    3.  展开**筛选器**参数，然后单击第二个**筛选器**节点。  
  
    4.  在属性窗格中，选择**员工姓名 [员工]** 从**标识符**列表。  
  
         ![设置筛选器参数标识符](../../adapters-and-accelerators/adapter-oracle-ebs/media/16-set-identifier.gif "16_Set_Identifier")  
  
3.  将标识符映射到的员工名称返回值。  
  
    1.  在元数据对象窗格中，展开**员工**节点，然后展开**方法**节点。  
  
    2.  展开**选择**方法，然后展开**参数**节点。  
  
    3.  展开**返回**节点，然后第二个**返回**节点，则**项**节点，，然后单击**名称**节点。  
  
    4.  在属性窗格中，选择**员工姓名 [员工]** 从**标识符**列表。  
  
#### <a name="to-create-a-specific-finder-method-instance-for-the-select-method"></a>若要创建特定的 Finder 方法实例选择的方法  
  
1.  在元数据对象窗格中，展开**员工**节点，然后**方法**节点。  
  
2.  展开**选择**节点，右键单击**实例**，然后选择**添加方法实例**以打开创建方法实例窗口。  
  
     ![添加方法实例](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")  
  
3.  在创建方法实例窗口中，选择**特定的 Finder**为**方法实例类型**。 选择**返回**为**返回 TypeDescriptor**。  
  
     ![添加特定的 Finder 方法实例](../../adapters-and-accelerators/adapter-oracle-ebs/media/17-specific-finder.gif "17_Specific_Finder")  
  
4.  单击 **“确定”**。  
  
5.  在属性窗格中，键入**SpeciFinder_Instance**为**名称**框。  
  
#### <a name="to-create-an-id-enumerator-method-instance-for-the-select-method"></a>若要创建 Select 方法 Id 枚举方法实例  
  
1.  在元数据对象窗格中，展开**员工**节点，然后**方法**节点。  
  
2.  展开**选择**节点，右键单击**实例**，然后选择**添加方法实例**以打开创建方法实例窗口。  
  
     ![添加方法实例](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")  
  
3.  在创建方法实例窗口中，选择**Id 枚举器**为**方法实例类型**。 选择**返回**为**返回 TypeDescriptor**。  
  
     ![创建一个 Id 枚举数方法实例](../../adapters-and-accelerators/adapter-oracle-ebs/media/18-id-enumerator.gif "18_ID_Enumerator")  
  
4.  单击 **“确定”**。  
  
5.  在属性窗格中，键入**IDEnumerator_Instance**为**名称**框。  
  
##  <a name="Defaults"></a>设置默认参数的方法实例  
 Select 方法要求你指定的列名称。 因此，你需要指定的默认值**COLUMN_NAMES**前面创建的 Finder、 特定的 Finder 和 Id 枚举器的方法实例的参数。 此外，还应指定的默认值**筛选器**Id 枚举器方法实例的参数。  
  
#### <a name="to-set-the-default-parameters-for-the-method-instances"></a>若要设置的方法实例的默认参数  
  
1.  在元数据对象窗格中，展开**员工**节点，然后展开**方法**节点。  
  
2.  展开**选择**节点，然后展开**参数**节点。  
  
3.  展开**COLUMN_NAMES**节点，，然后选择**COLUMN_NAMES**参数。  
  
4.  在属性窗格中，单击省略号按钮 （…） 针对**DefaultValues**框。  
  
5.  在**DefaultValueView 集合编辑器**对话框中，单击**添加**，在属性窗格中，单击**Finder_Instance**中**SelectMethodInstance**列表。  
  
     ![指定默认值为 Finder 实例](../../adapters-and-accelerators/adapter-oracle-ebs/media/19-finderinstance-defaults.gif "19_FinderInstance_Defaults")  
  
6.  类型`*`中**值**框。  
  
7.  同样，重复步骤 5 和 6 以添加默认值**SpecificFinder_Instance**和**IDEnumerator_Instance**方法实例。  
  
8.  在**DefaultValueView 集合编辑器**对话框中，单击**确定**。  
  
9. 接下来，添加的默认值**筛选器**参数**IDEnumerator_Instance**方法实例。 展开**筛选器**节点，，然后选择**筛选器**参数。  
  
10. 在属性窗格中，单击省略号按钮 （…） 针对**DefaultValues**框。  
  
11. 在**DefaultValueView 集合编辑器**对话框中，单击**添加**，在属性窗格中，单击**IDEnumerator_Instance**中**SelectMethodInstance**列表。  
  
12. 类型`%`中**值**框。  
  
     ![Id 枚举器实例的默认值](../../adapters-and-accelerators/adapter-oracle-ebs/media/20-idenumeratorinstance-defaults.gif "20_IDEnumeratorInstance_Defaults")  
  
13. 在**DefaultValueView 集合编辑器**对话框中，单击**确定**。  
  
##  <a name="SSO"></a>为连接到 Oracle E-business Suite 向上上单一登录设置  
 在本主题中执行的所有过程完成后，你将创建可以导入 SharePoint 应用程序的应用程序定义文件。 从应用程序，你调用的方法从 Oracle E-business Suite 检索相关数据。 若要启用此功能，必须在 SharePoint 应用程序中创建 Oracle E-business Suite 中的用户和用户之间的映射。 已导入的应用程序定义文件后，可以在 SharePoint 管理中心控制台中创建此映射。  
  
 但是，若要创建映射必须设置一个属性**SecondarySsoApplicationId**在业务数据目录定义编辑器中。  
  
#### <a name="to-set-the-secondaryssoapplicationid-property"></a>若要设置 SecondarySsoApplicationId 属性  
  
1.  在元数据对象窗格中，展开**MS_SAMPLE_EMPLOYEE**节点，然后展开**实例**节点。  
  
2.  单击**MS_SAMPLE_EMPLOYEE_Instance**，然后在属性窗格中，单击针对省略号 （...） 按钮**属性**框。  
  
3.  在**PropertyView 集合编辑器**对话框中，单击**添加**，然后在属性窗格中，键入**SecondarySsoApplicationId**为**名称**框。 同样，键入**OracleSSO**为**PropertyValue**框。 选择**System.String**为**类型**框。  
  
     ![添加 SSO 属性](../../adapters-and-accelerators/adapter-oracle-ebs/media/21-sso.gif "21_SSO")  
  
4.  单击 **“确定”**。  
  
##  <a name="Export"></a>将应用程序定义导出到文件  
 现在已创建包含 Oracle E-business Suite 实例元数据的应用程序定义。 必须将此定义导出到一个 XML 文件，其中可以导入到 Microsoft Office SharePoint Server。  
  
#### <a name="to-export-the-application-definition-to-a-file"></a>若要将应用程序定义导出到文件  
  
1.  在元数据对象窗格中，右键单击**MS_SAMPLE_EMPLOYEE**节点，，然后单击**导出**。  
  
2.  将文件保存为 Employee.xml。  
  
## <a name="next-steps"></a>后续步骤  
 你现在必须创建 SharePoint 应用程序从 Oracle E-business Suite 检索数据。 有关说明，请参阅[步骤 3： 创建一个 SharePoint 应用程序检索数据从 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)。  
  
## <a name="see-also"></a>另请参阅  
 [教程： 从 SharePoint 站点上的 Oracle E-business Suite 显示数据](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)