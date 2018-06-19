---
title: 步骤 2： 为 Siebel 业务组件操作创建应用程序定义文件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75d34c48-0f2a-42e4-a60b-e04bcf2404e1
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3bd1eaac434f4fc6bda55f6ab290740147d91997
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22227029"
---
# <a name="step-2-create-an-application-definition-file-for-siebel-business-component-operations"></a>步骤 2： 为 Siebel 业务组件操作创建应用程序定义文件
![步骤 2 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **完成时间：** 15 分钟  
  
 **目标：** 业务数据目录公开，并将从-的业务线 (LOB) 应用程序的数据合并到门户。 若要将此数据合并到您的门户网站，必须在生成应用程序定义文件，可以使用 Microsoft Office SharePoint Server。  
  
 业务数据目录定义编辑器工具，可为业务数据目录中创建应用程序定义文件。 此工具会自动生成的 XML 定义文件。 因此，无需手动创建该文件在 XML 编辑器。  
  
 要创建 Microsoft Office SharePoint Server 应用程序的目的是对执行查询操作帐户在业务组件，若要检索的记录列表。 若要实现此目的，必须完成一的组任务在业务数据目录定义编辑器中。 本主题提供有关如何执行这些任务的说明。  
  
## <a name="prerequisites"></a>先决条件  
  
-   你必须作为 Microsoft Office SharePoint Server 2007 SDK 的一部分安装的业务数据目录定义编辑器。 你可以下载 SDK 从[http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130)。  
  
-   你应已发布 WCF 服务中所述[步骤 1： 发布 Siebel 业务组件操作作为 WCF 服务](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)。  
  
## <a name="creating-an-application-definition-file"></a>创建应用程序定义文件  
 本部分提供分步说明来创建 WCF 服务应用程序定义文件。  
  
### <a name="connect-to-the-wcf-service-and-create-entities"></a>连接到 WCF 服务，并创建实体  
 你必须连接到要提取 Web 服务描述语言 (WSDL) 服务的 WCF 服务。 从 WSDL，业务数据目录定义编辑器中提取方法。 这些方法可以用于创建实体。 对于此示例中，你必须创建查询操作帐户在业务组件上的一个实体。  
  
##### <a name="to-connect-to-the-wcf-service-and-create-entities"></a>若要连接到 WCF 服务，并创建实体  
  
1.  启动业务数据目录定义编辑器。 上**启动**菜单上，单击**Microsoft 业务数据目录定义编辑器**。  
  
2.  在工具中，单击**添加 LOB 系统**。  
  
3.  在添加 LOB 系统窗口中，单击**连接到 web 服务**。  
  
4.  在 URL 框中，键入 WCF 服务的 URL。 该 URL 必须采用以下格式：  
  
    ```  
    https://<computer_name>/Siebel_Account/BusinessObjects_Account_Account_Operation.svc?wsdl  
    ```  
  
     其中，BusinessObjects_Account_Account_Operation.svc 是创建 Siebel 协定的服务文件。  
  
     当你测试是否成功中, 所述发布 WCF 服务时，必须键入的 URL 才可用[步骤 1： 发布 Siebel 业务组件操作作为 WCF 服务](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)。  
  
5.  单击 **“连接”**。  
  
6.  单击**添加 Web 方法**选项卡以查看在 WCF 适配器服务开发向导中选择的操作。 你将看到**查询**方法。  
  
     ![将 web 方法添加到 BDC 应用程序](../../adapters-and-accelerators/adapter-siebel/media/f9505cd3-67e3-4f99-b189-d010322a3137.gif "f9505cd3-67e3-4f99-b189-d010322a3137")  
  
7.  拖动**查询**方法到设计图面，然后单击**确定**。  
  
8.  在**输入 LOB 系统的名称**对话框中，键入一个名称中**LOB 系统名称**框。 对于此示例中，键入`Siebel_Account`，然后单击**确定**。 一个实体， **Entity0**，创建在业务数据目录定义编辑器中。  
  
    > [!IMPORTANT]
    >  业务数据目录定义编辑器工具并不处理枚举的数据类型。 因此，业务数据目录定义编辑器工具导入字段直到它遇到枚举的数据类型，并忽略其余的字段。 业务数据目录定义编辑器工具还提供了一个错误。 你可以忽略此错误，然后通过单击确定继续。 你可以手动添加必填的字段在应用程序定义文件中在更高版本的阶段。  
  
9. 更改要使用更多的友好名称的实体名称。 对于此示例中，更改**Entity0**到**帐户**。  
  
    1.  展开**Siebel_Account**节点，然后展开**实体**节点。  
  
    2.  选择**Entity0**节点。  
  
    3.  在属性窗格中，键入**帐户**中**名称**字段。  
  
         ![重命名实体](../../adapters-and-accelerators/adapter-siebel/media/44eda1de-b348-4421-9c51-0355b51f4a90.gif "44eda1de-b348-4421-9c51-0355b51f4a90")  
  
### <a name="specify-user-name-and-password-headers-for-methods"></a>为方法中指定用户名和密码标头  
 当 Siebel 系统中创建所选的业务组件操作的 WCF 服务，你指定用户名称和密码标头为终结点行为配置的一部分 ([步骤 1： 发布 Siebel 业务组件操作作为 WCF 服务](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md))。 必须指定方法属性的相同值。  
  
##### <a name="to-specify-user-name-and-password-headers-for-the-query-method"></a>若要指定用户名称和密码标头的查询方法  
  
1.  在元数据对象窗格中，展开**帐户**节点，然后展开**方法**节点。  
  
2.  单击**查询**节点，然后在属性窗格中单击针对省略号 （...） 按钮**属性**字段。  
  
3.  在 PropertyView 集合编辑器对话框中，单击**添加**，然后在属性窗格中，键入`HttpHeaderUserName`为**名称**字段。 同样，键入`MyUserHeader`为**PropertyValue**字段。 选择**System.String**为**类型**字段。  
  
     ![将属性添加](../../adapters-and-accelerators/adapter-sap/media/9eef32ac-8a93-45dc-8d07-12b7dbf961ba.gif "9eef32ac-8a93-45dc-8d07-12b7dbf961ba")  
  
4.  在 PropertyView 集合编辑器窗口中，单击**添加**，然后在属性窗格中，键入`HttpHeaderPassword`为**名称**字段。 同样，键入`MyPassHeader`为**PropertyValue**字段。 选择**System.String**为**类型**字段。  
  
5.  单击 **“确定”**。  
  
### <a name="set-up-single-sign-on-for-connecting-to-a-siebel-system"></a>为连接到 Siebel 系统上单一登录设置  
 在本主题中执行的所有过程完成后，你将创建的应用程序定义可导入 SharePoint 应用程序的 XML。 从应用程序，将调用 （作为 Web 方法公开） 的 Siebel 业务组件操作从 Siebel 系统中检索相关数据。 若要启用此功能，必须在 SharePoint 应用程序中创建 Siebel 系统中的用户和用户之间的映射。 已导入的应用程序定义 XML 后，可以在 SharePoint 管理中心网站中创建此映射。  
  
 但是，若要创建映射必须设置一个属性**SecondarySsoApplicationId**在业务数据目录定义编辑器中。  
  
##### <a name="to-set-the-secondaryssoapplicationid-property"></a>若要设置 SecondarySsoApplicationId 属性  
  
1.  在元数据对象窗格中，展开**Siebel_Account**节点，然后展开**实例**节点。  
  
2.  单击**Siebel_Account_Instance**在属性窗格中单击省略号 （…） 按钮针对**属性**字段。  
  
3.  在 PropertyView 集合编辑器窗口中，单击**添加**，然后在属性窗格中，键入**SecondarySsoApplicationId**为**名称**字段。 同样，键入**SiebelSSO**为**PropertyValue**字段。 选择**System.String**为**类型**字段。  
  
     ![添加 SSO 属性](../../adapters-and-accelerators/adapter-siebel/media/59ce70eb-498f-406b-965d-c273c2d6ed14.gif "59ce70eb-498f-406b-965d-c273c2d6ed14")  
  
4.  单击 **“确定”**。  
  
### <a name="requirement-perform-a-query-operation-on-the-account-business-component"></a>要求： 执行帐户在业务组件上的查询操作  
 此示例的第一个要求是创建用于执行查询操作帐户在业务组件上的应用程序定义。 若要实现此要求，必须执行以下一组任务：  
  
-   在查询方法中，创建筛选器，并将其映射到对其执行查询操作的参数。 对于帐户业务组件，你将执行查询时使用**SearchExpr**参数。 因此，将映射到筛选器**SearchExpr**参数。  
  
-   创建查询方法的 Finder 方法实例。 Finder 方法检索基于筛选器的记录的列表。  
  
##### <a name="to-create-a-filter-and-map-it-to-the-searchexpr-parameter"></a>创建筛选器，并将其映射到 SearchExpr 参数  
  
1.  创建筛选器的查询方法。  
  
    1.  在元数据对象窗格中，展开**帐户**节点，然后展开**方法**节点。  
  
    2.  展开的查询方法中，右键单击**筛选器**，然后单击**添加筛选器**。  
  
         ![向方法添加筛选器](../../adapters-and-accelerators/adapter-siebel/media/9cf7ccfd-6da0-44b7-b522-df327a74e7a2.gif "9cf7ccfd-6da0-44b7-b522-df327a74e7a2")  
  
    3.  在属性窗格中，键入`SearchExpression`为**名称**字段。  
  
    4.  有关**FilterType**属性中，选择**等于**。  
  
         ![指定筛选器名称和类型](../../adapters-and-accelerators/adapter-siebel/media/9faa18e1-4d27-4ee4-960a-458f978812a7.gif "9faa18e1-4d27-4ee4-960a-458f978812a7")  
  
2.  映射到筛选器**SearchExpr**查询方法中的参数。  
  
    1.  在元数据对象窗格中，展开**帐户**节点，然后展开**方法**节点。  
  
    2.  展开查询方法，然后展开**参数**节点。  
  
    3.  展开**AccountQueryInputRecord**节点，然后展开第二个**AccountQueryInputRecord**节点。  
  
    4.  单击**SearchExpr**节点，然后在属性窗格中，选择**SearchExpression**从**FilterDescriptor**列表。  
  
         ![将参数映射到筛选器](../../adapters-and-accelerators/adapter-siebel/media/199c8ba7-d0e8-4fb4-9d73-9cf548512498.gif "199c8ba7-d0e8-4fb4-9d73-9cf548512498")  
  
        > [!IMPORTANT]
        >  **AccountQueryInputRecord**还包含**QueryFields**节点，后者又包含**项**节点。 你必须删除**项**节点，否则帐户在业务组件上的查询操作可能不会得到所需的结果。 若要删除**项**节点，右键单击该节点，然后选择**删除**。  
  
##### <a name="to-create-a-finder-method-instance-for-query-method"></a>若要创建查询方法的 Finder 方法实例  
  
1.  在元数据对象窗格中，展开**帐户**节点，然后展开**方法**节点。  
  
2.  展开**查询**节点，右键单击**实例**，然后单击**添加方法实例**以打开创建方法实例窗口。  
  
     ![添加 Finder 方法实例](../../adapters-and-accelerators/adapter-siebel/media/c90e7784-4fb7-4eb5-baf5-efbefba4bb1f.gif "c90e7784-4fb7-4eb5-baf5-efbefba4bb1f")  
  
3.  在创建方法实例窗口中，单击**Finder**为**方法实例类型**。  
  
4.  单击**返回**从**返回 TypeDescriptor**部分。  
  
     ![添加 Finder 方法实例](../../adapters-and-accelerators/adapter-siebel/media/e8343988-d7c1-4b04-85b0-ca7d07097490.gif "e8343988-d7c1-4b04-85b0-ca7d07097490")  
  
5.  单击 **“确定”**。  
  
6.  在属性窗格中，键入`QueryAccount`为**名称**字段。  
  
     ![指定方法实例的名称](../../adapters-and-accelerators/adapter-siebel/media/401223f3-806f-4010-8646-d5ac0c0e9f67.gif "401223f3-806f-4010-8646-d5ac0c0e9f67")  
  
### <a name="remove-the-parameters-of-systemnullable-type"></a>删除 System.Nullable 类型的参数  
 查询函数的返回参数可能包含属于 System.Nullable 类型的参数。 由于这些参数中的应用程序定义的可能会显示在 SharePoint 门户网站上的 Siebel 数据时遇到错误。 因此，你必须从应用程序定义删除 System.Nullable 类型的参数。  
  
 此外，对于 System.Nullable 类型的每个参数，业务数据目录定义编辑器创建 System.Boolean 类型的另一个参数，并将"指定"追加到的参数名称。 例如，该参数 AccountRole 属于 System.Nullable 类型。 因此，业务数据目录定义编辑器将 AccountRoleSpecified 参数添加到的参数的列表。 你必须删除以及此类参数。  
  
> [!NOTE]
>  你可以看到通过选择参数在业务数据目录定义编辑器中，并查看的值类型的参数**TypeName**在属性窗格中的属性。  
  
> [!NOTE]
>  如果应用程序不包含 System.Nullable 类型的任何参数，则可以跳过此步骤。  
  
##### <a name="to-remove-the-parameters-of-systemnullable-type-for-the-query-method"></a>若要删除的查询方法的 System.Nullable 类型的参数  
  
1.  在元数据对象窗格中，展开**帐户**节点，然后展开**方法**节点。  
  
2.  展开**查询**节点，然后展开**参数**节点。  
  
3.  展开**返回**节点，然后展开第二个**返回**节点。  
  
4.  右键单击你想要删除，然后选择的参数**删除**。  
  
5.  在对话框中，单击**确定**。  
  
### <a name="export-the-application-definition-to-a-file"></a>将应用程序定义导出到文件  
 现在已创建包含 Siebel 系统实例元数据的应用程序定义。 必须将此定义导出到一个 XML 文件，其中可以导入到 Microsoft Office SharePoint Server。  
  
##### <a name="to-export-the-application-definition-to-a-file"></a>若要将应用程序定义导出到文件  
  
1.  右键单击**Siebel_Account**在元数据对象窗格中，然后单击的节点**导出**。  
  
2.  将文件保存为 Siebel_Account.xml。  
  
### <a name="modify-the-application-definition-file-to-include-specific-parameters"></a>修改要包含特定参数的应用程序定义文件  
 如本主题中前面所述，业务数据目录定义编辑器工具将不处理枚举的数据类型。 业务数据目录定义编辑器工具导入字段，直到它遇到枚举的数据类型，并忽略其余的字段。 因此，您要在你的应用程序中的某些字段可能被取消。 你可以手动编辑要包括这些字段的应用程序定义文件。  
  
> [!NOTE]
>  你必须确保要添加的参数是由 WCF 适配器服务开发向导在生成的.cs 文件中存在[步骤 1： 发布 Siebel 业务组件操作作为 WCF 服务](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)。  
  
 在此应用程序定义文件中，你将添加或删除返回参数**QueryAccount**方法。  
  
##### <a name="to-modify-the-application-definition-file"></a>若要修改的应用程序定义文件  
  
1.  通过使用打开应用程序定义文件，Siebel_Account.xml，[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或任何其他编辑器中。  
  
2.  修改要替换的参数的应用程序定义文件**QueryAccount**方法。  
  
    1.  在应用程序定义文件中，搜索以下：  
  
        ```  
        <TypeDescriptor TypeName="BDC.AccountQueryRecord,Siebel_Account" Name="Item">  
        ```  
  
    2.  在`<TypeDescriptors>`标记中，将现有`<TypeDescriptor>`替换为以下元素：  
  
        ```  
  
        <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Id" />  
        <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Country" />  
        <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Name" />  
        <TypeDescriptor TypeName="System.String, mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=<token>" Name="Location" />  
        ```  
  
    3.  保存并关闭该文件。  
  
    > [!TIP]
    >  你可以导入回中才能看到新添加的字段的业务数据目录定义编辑器工具的更新的应用程序定义文件。 但是，在导入之前你将需要从业务数据目录定义编辑器工具删除现有的"Siebel_Account"应用程序。  
  
## <a name="next-steps"></a>后续步骤  
 你现在必须创建 SharePoint 应用程序从 Siebel 系统检索数据。 请参阅[步骤 3： 创建一个 SharePoint 应用程序检索数据从 Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md)有关的说明。  
  
## <a name="see-also"></a>另请参阅  
 [教程 1： 从 SharePoint 站点上的 Siebel 系统提供数据](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)