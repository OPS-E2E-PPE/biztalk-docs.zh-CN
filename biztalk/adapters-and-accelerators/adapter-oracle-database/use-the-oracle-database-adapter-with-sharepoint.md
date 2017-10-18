---
title: "将用于 SharePoint 的 Oracle 数据库适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 254204e5-3b5d-4e70-97ab-817660d1206a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a5866344e666c9e9cb49af6c6d99211774a2758
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2017
---
# <a name="use-the-oracle-database-adapter-with-sharepoint"></a>将用于 SharePoint 的 Oracle 数据库适配器
WCF 适配器服务开发向导[!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]为 Oracle 数据库和 Oracle E-business Suite Microsoft BizTalk 适配器将直接使用作为 Microsoft SharePoint 中的外部数据源启用 Microsoft BizTalk 适配器。 添加服务开发支持此功能启动向导时与**WCF 适配器服务**用于创建新 Visual C# Web 中的站点模板[!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]。 此模板是附带[!INCLUDE[adapterpacknoversion_md](../../includes/adapterpacknoversion-md.md)]。 你还必须安装 Microsoft Windows Communication Foundation (WCF) 的业务线 (LOB) 适配器 SDK。  
  
## <a name="sharepoint-operation-support"></a>SharePoint 操作支持  
 适配器服务开发向导将生成适用于 Microsoft SharePoint 的特殊服务协定为 Oracle 适配器。 此向导将生成服务协定，其中包括对与 Microsoft SharePoint 集成适配器执行以下操作：  
  
-   **创建：** CreateItem_ 操作支持。  
  
-   **阅读：** ReadItem_ 操作支持。  
  
-   **更新：** UpdateItem_ 操作支持。  
  
-   **删除：** DeleteItem_ 操作支持。  
  
-   **查询：** ReadList 操作支持。  
  
-   **相关联：** Associate_ 操作支持。  
  
 在使用 Microsoft BizTalk 适配器 Oracle 数据库作为的示例生成以下服务协定。 适配器已配置为提供对 EMP 表的访问  
  
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
 这些步骤提供了一个示例使用 WCF 适配器服务的开发向导中，若要创建新的 WCF web 服务的 Oracle 数据库承载 Microsoft BizTalk 适配器。 服务协定将包含操作与 Sharepoint 直接兼容。 以便可以直接使用它作为外部数据源。 适配器已配置为使用 Oracle 数据库使用进行身份验证**SCOTT**帐户。 如果**SCOTT**锁定帐户，你可以通过以 sysdba 身份登录到 SQL Plus 解锁帐户。  
  
```  
<Oracle Installation Bin Directory>\Sqlplus.exe SYS AS SYSDBA  
```  
  
 然后运行以下命令。  
  
```  
SQL> ALTER USER scott ACCOUNT UNLOCK;  
```  
  
#### <a name="create-the-new-web-site-project"></a>创建新的网站项目  
  
1.  打开 Visual Studio。   
  
2.  在 Visual Studio 中，在**文件**菜单上，选择**新建**，然后单击**项目**。  
  
3.  在**新项目**对话框框中，展开**其他语言**单击**Visual C#**。 查找**WCF 适配器服务**在模板列表，然后单击以选中它。  
  
    > [!NOTE]
    >  **WCF 适配器服务**未提供模板如果[!INCLUDE[adapterpackcurrent](../../includes/adapterpackcurrent-md.md)]未安装。 在 x64 系统中，安装的 x86 和 x64 版本[!INCLUDE[adapterpackcurrent](../../includes/adapterpackcurrent-md.md)]。  
  
4.  指定**ScottEMP**作为名称，然后单击**确定**。 **WCF 适配器服务开发向导**启动。  
  
5.  上**简介**页上，单击**下一步**。  
  
6.  上**选择操作**页上，指定**oracleDBBinding**绑定。  
  
7.  单击**配置**按钮。 **配置适配器**显示对话框。  
  
8.  上**安全**选项卡上，选择**用户名**中**客户端凭据类型**下拉列表框。  
  
9. 输入**SCOTT**用户名称和 SCOTT 帐户输入正确的密码。 SCOTT 帐户的默认密码是**tiger**。  
  
10. 单击**URI 属性**选项卡上，输入中的 Oracle 服务器的 IP 地址或主机名**ServerAddress**框。  
  
11. 输入中的正确 Oracle 数据库服务实例名称**ServiceName**框。 你可以复制的实例名称信息从 Oracle Enterprise Manager。  
  
12. 按**确定**按钮上**配置适配器**对话框  
  
13. 上**选择操作**页的向导中，单击**连接**按钮并等待几分钟要为 Oracle 数据库生成的类别。  
  
14. 将类别添加中后**选择类别**列表中，向下滚动到**SCOTT**并将其展开。 然后展开**表**单击**EMP**表条目。  
  
15. 在**可用类别和操作**列表，在列表中选择的所有操作并单击**添加**按钮。 所有操作都添加到**都添加类别和操作**列表。  
  
16. 上**选择操作**页上，单击**下一步**按钮。  
  
17. 上**配置服务和终结点行为**页上，设置**UseServiceCertificate**服务行为到**false**对于此示例。 然后单击**下一步**按钮。  
  
18. 上**配置服务终结点绑定和地址**页上，单击**应用**按钮。 然后单击**下一步**按钮。  
  
19. 上**摘要**页上，单击**完成**按钮。  
  
20. 单击**生成**菜单选项，然后单击**生成解决方案**。 验证项目生成成功并且没有错误。  
  
## <a name="publish-the-new-service-to-iis"></a>将新的服务发布到 IIS  
 对于此示例在将发布到本地 IIS web 服务器的适配器主机服务。  
  
1.  在 Visual Studio 的解决方案资源管理器，右键单击**ScottEmp**项目，然后单击**属性**。 将显示项目设计器选项卡。  
  
2.  单击**Web**选项卡，然后单击**使用本地 IIS Web 服务器**选项。  
  
3.  单击**创建虚拟目录**按钮。  
  
4.  打开 web 浏览器到服务地址**http://localhost/ScottEmp/ISCOTT_EMP.svc**。 你应该会收到一条消息"你已创建的服务"，该值指示适配器承载于 IIS 中。  
  
## <a name="add-the-external-data-source-to-a-sharepoint-site-using-sharepoint-designer"></a>将外部数据源添加到 SharePoint 站点使用 SharePoint Designer  
 本部分介绍如何将 WCF 服务作为外部数据源添加到新的网站使用 SharePoint Designer。  
  
  
1.  打开 SharePoint Designer 并创建新网站。  
  
2.  在 SharePoint 设计器中，展开**导航**单击**外部内容类型**中**站点对象**列表。  
  
3.  单击**外部内容类型**菜单按钮创建新的外部内容类型。  
  
4.  单击旁边的文本**名称**编辑新的外部内容类型的名称。 输入**OracleEMP**的名称。  
  
5.  单击旁边的文本链接**外部系统**表示**单击此处以查看外部数据源和操作。**。 这将打开操作设计器中为 OracleEMP 外部内容类型。  
  
6.  单击**添加连接**发现屏幕上的按钮。  
  
7.  在外部数据源类型选择对话框中，选择**WCF 服务**单击**确定**按钮。  
  
8.  在 WCF 连接对话框中，在**服务元数据 URL**框中输入**https://localhost/ScottEmp/ISCOTT_EMP.svc?wsdl**  
  
9. 在**服务终结点 URL**框中输入**https://localhost/ScottEmp/ISCOTT_EMP.svc**  
  
10. 单击**确定**按钮以关闭 WCF 连接对话框。  
  
11. 后填充了数据源信息，则展开**https://localhost/ScottEmp/ISCOTT_EMP.svc**数据源，并展开**Web 方法**。  
  
12. 右键单击**ReadList** Web 方法，并单击**新读列表操作**。 读取列表配置对话框被启动。  
  
13. 在读取列表对话框中单击**返回参数**单击**EMPNO**中数据源元素。 单击**映射到标识符**。  
  
14. 单击**完成**在读取列表对话框中。  
  
15. 通过键入保存新的外部数据源**Ctrl + s**。  
  
#### <a name="test-the-external-data-source-connection"></a>测试外部数据源连接  
  
1.  在新的网站上，单击**创建列出和窗体**按钮。 创建列表和窗体 OracleEMP 对话框将出现。  
  
2.  输入**OracleEMP_List**列表名称然后单击**确定**按钮。  
  
3.  列表是在创建后，单击**摘要视图**菜单上的按钮。  
  
4.  单击**OracleEMP_List**下外部列表。  
  
5.  单击**在浏览器中的预览**若要测试的适配器 ReadList 操作菜单上的按钮。  
  
## <a name="troubleshoot"></a>故障排除
  
-   在 64 位计算机上，你必须确保还安装了 32 位 Oracle 客户端组件。 这是因为将作为在开发过程中需要访问 32 位组件的 32 位进程运行 Visual Studio 和它的向导。