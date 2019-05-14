---
title: 使用包含 SharePoint 的 Oracle 数据库适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 254204e5-3b5d-4e70-97ab-817660d1206a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ca498313f74ac863cfb8d3c3846cb590cddebe8
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528984"
---
# <a name="use-the-oracle-database-adapter-with-sharepoint"></a>使用包含 SharePoint 的 Oracle 数据库适配器
WCF 适配器服务开发向导为[!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]使 Oracle 数据库和用于 Oracle E-business Suite 的 Microsoft BizTalk 适配器来直接被作为 Microsoft SharePoint 中外部数据源可以使用 Microsoft BizTalk 适配器。 使用启动添加服务开发向导支持此功能**WCF 适配器服务**模板，用于创建新 Visual C# Web 站点中[!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]。 该模板是附带[!INCLUDE[adapterpacknoversion_md](../../includes/adapterpacknoversion-md.md)]。 此外必须安装 Microsoft Windows Communication Foundation (WCF) 业务线 (LOB) 适配器 SDK。  
  
## <a name="sharepoint-operation-support"></a>SharePoint 操作支持  
 适配器服务开发向导将生成适用于 Microsoft SharePoint 的 Oracle 适配器的特殊服务协定。 向导将生成服务协定，其中包括用于与 Microsoft SharePoint 集成适配器的以下操作：  
  
- **创建：** CreateItem_ 操作支持。  
  
- **读取：** ReadItem_ 操作支持。  
  
- **更新：** UpdateItem_ 操作支持。  
  
- **删除：** DeleteItem_ 操作支持。  
  
- **查询：** ReadList 操作支持。  
  
- **将相关联：** Associate_ 操作支持。  
  
  下面的服务协定使用生成的 Microsoft BizTalk 适配器对 Oracle 数据库作为示例。 适配器已配置为提供访问权限的 EMP 表  
  
```  
    [System.ServiceModel.ServiceContractAttribute()]  
    public interface ISCOTT_EMP {  
  
    [System.ServiceModel.OperationContractAttribute()]  
    SCOTT_EMP_Record[] ReadList(System.Nullable<int> Limit);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    void CreateItem(SCOTT_EMP_Record Input);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    SCOTT_EMP_Record[] ReadItem_EMPNO(System.Nullable<decimal> EMPNO);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    void UpdateItem_EMPNO(SCOTT_EMP_Record Input);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    void DeleteItem_EMPNO(System.Nullable<decimal> EMPNO);  
  
    [System.ServiceModel.OperationContractAttribute()]  
    SCOTT_EMP_Record[] Associate_DEPTNO(System.Nullable<decimal> DEPTNO);  
}  
```  
  
## <a name="create-a-new-web-site-to-host-the-oracle-database-in-iis"></a>创建新网站以承载在 IIS 中的 Oracle 数据库  
 这些步骤提供了使用 WCF 适配器服务开发向导中，若要创建新的 Oracle 数据库承载 Microsoft BizTalk 适配器的 WCF web 服务的示例。 服务协定将包含与 Sharepoint 直接兼容的操作。 以便可以直接使用它作为外部数据源。 适配器已配置为使用 Oracle 数据库使用进行身份验证**SCOTT**帐户。 如果**SCOTT**锁定帐户，可以通过以 sysdba 身份登录到 SQL Plus 解锁帐户。  
  
```  
<Oracle Installation Bin Directory>\Sqlplus.exe SYS AS SYSDBA  
```  
  
 然后运行以下命令。  
  
```  
SQL> ALTER USER scott ACCOUNT UNLOCK;  
```  
  
#### <a name="create-the-new-web-site-project"></a>创建新网站项目  
  
1. 打开 Visual Studio。   
  
2. 在 Visual Studio 中，在**文件**菜单中，选择**新建**，然后单击**项目**。  
  
3. 在中**新的项目**对话框框中，展开**其他语言**然后单击**Visual C#**。 查找**WCF 适配器服务**在模板列表中，单击以选中它。  
  
   > [!NOTE]
   >  **WCF 适配器服务**未提供模板如果[!INCLUDE[adapterpackcurrent](../../includes/adapterpackcurrent-md.md)]未安装。 在 x64 系统中，安装的 x86 和 x64 版本[!INCLUDE[adapterpackcurrent](../../includes/adapterpackcurrent-md.md)]。  
  
4. 指定**ScottEMP**作为名称，然后单击**确定**。 **WCF 适配器服务开发向导**启动。  
  
5. 上**简介**页上，单击**下一步**。  
  
6. 上**选择操作**页上，指定**oracleDBBinding**绑定。  
  
7. 单击**配置**按钮。 **配置适配器**显示对话框。  
  
8. 上**安全**选项卡上，选择**用户名**中**客户端凭据类型**下拉列表框。  
  
9. 输入**SCOTT**用户名称和 SCOTT 帐户输入正确的密码。 SCOTT 帐户的默认密码是**tiger**。  
  
10. 单击**URI 属性**选项卡上，输入在 Oracle 服务器的 IP 地址或主机名**ServerAddress**框。  
  
11. 输入中的正确 Oracle 数据库服务实例名称**ServiceName**框。 从 Oracle 企业管理器中，可以将复制的实例名称信息。  
  
12. 按**确定**按钮**配置适配器**对话框  
  
13. 上**选择操作**页的向导中，单击**Connect**按钮，然后等待类别的 Oracle 数据库生成的一段时间。  
  
14. 将类别添加中后**选择一个类别**列表中，向下滚动到**SCOTT**并将其展开。 然后展开**表**然后单击**EMP**表条目。  
  
15. 在中**可用类别和操作**列表中，选择列表中的所有操作，单击**添加**按钮。 所有操作都添加到**都添加的类别和操作**列表。  
  
16. 上**选择操作**页上，单击**下一步**按钮。  
  
17. 上**配置服务和终结点行为**页上，将**UseServiceCertificate**服务到行为**false**对于此示例。 然后单击**下一步**按钮。  
  
18. 上**配置服务终结点绑定和地址**页上，单击**应用**按钮。 然后单击**下一步**按钮。  
  
19. 上**摘要**页上，单击**完成**按钮。  
  
20. 单击**构建**菜单选项，然后单击**生成解决方案**。 验证项目生成成功，但没有错误。  
  
## <a name="publish-the-new-service-to-iis"></a>将新服务发布到 IIS  
 对于此示例将适配器主机服务发布到本地 IIS web 服务器。  
  
1.  在 Visual Studio 的解决方案资源管理器，右键单击**ScottEmp**项目，然后单击**属性**。 显示项目设计器选项卡。  
  
2.  单击**Web**选项卡，然后单击**使用本地 IIS Web 服务器**选项。  
  
3.  单击**创建虚拟目录**按钮。  
  
4.  服务地址 web 浏览器中打开**http://localhost/ScottEmp/ISCOTT_EMP.svc**。 您应收到一条消息指出"您已创建服务"，该值指示适配器承载于 IIS 中。  
  
## <a name="add-the-external-data-source-to-a-sharepoint-site-using-sharepoint-designer"></a>将外部数据源添加到 SharePoint 站点使用 SharePoint Designer  
 本部分介绍如何将 WCF 服务作为外部数据源添加到新的 Web 站点使用 SharePoint Designer。  
  
  
1.  打开 SharePoint Designer 并创建新的 Web 站点。  
  
2.  在 SharePoint 设计器中，展开**导航**然后单击**外部内容类型**中**站点对象**列表。  
  
3.  单击**外部内容类型**菜单按钮来创建一个新的外部内容类型。  
  
4.  单击旁边的文本**名称**可以编辑新的外部内容类型的名称。 输入**OracleEMP**的名称。  
  
5.  单击旁边的文本链接**外部系统**假定**单击此处以查看外部数据源和操作。**。 这将打开 OracleEMP 外部内容类型操作设计器。  
  
6.  单击**添加连接**发现屏幕上的按钮。  
  
7.  在选择外部数据源类型对话框中，选择**WCF 服务**然后单击**确定**按钮。  
  
8.  在 WCF 连接对话框中，在**服务元数据 URL**框中输入 **https://localhost/ScottEmp/ISCOTT_EMP.svc?wsdl**  
  
9. 在中**服务终结点 URL**框中输入 **https://localhost/ScottEmp/ISCOTT_EMP.svc**  
  
10. 单击**确定**按钮以关闭 WCF 连接对话框。  
  
11. 数据源信息填充后，展开**https://localhost/ScottEmp/ISCOTT_EMP.svc**数据源，并展开**Web 方法**。  
  
12. 右键单击**ReadList** Web 方法，并单击**新读取列表操作**。 启动读取列表配置对话框。  
  
13. 在读取列表对话框中单击**返回参数**然后单击**EMPNO**数据源元素中。 单击**映射到标识符**。  
  
14. 单击**完成**读取列表对话框中。  
  
15. 通过键入来保存新的外部数据源**Ctrl + s**。  
  
#### <a name="test-the-external-data-source-connection"></a>测试外部数据源连接  
  
1.  在新的网站上，单击**创建列表和窗体**按钮。 创建列表和用于 OracleEMP 对话框窗体将出现。  
  
2.  输入**OracleEMP_List**的列表名称，然后单击**确定**按钮。  
  
3.  一旦创建列表，请单击**摘要视图**菜单上的按钮。  
  
4.  单击**OracleEMP_List**下外部列表。  
  
5.  单击**浏览器中的预览**测试适配器的 ReadList 操作菜单上的按钮。  
  
## <a name="troubleshoot"></a>故障排除
  
-   64 位计算机上必须确保也安装 32 位 Oracle 客户端组件。 这是因为将作为 32 位进程在开发过程中需要访问 32 位组件运行 Visual Studio 和它的向导。