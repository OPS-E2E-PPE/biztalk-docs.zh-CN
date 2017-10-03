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
ms.openlocfilehash: 2cf5be42a008cadba648739037797160386a42fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="use-the-oracle-database-adapter-with-sharepoint"></a><span data-ttu-id="dfd49-102">将用于 SharePoint 的 Oracle 数据库适配器</span><span class="sxs-lookup"><span data-stu-id="dfd49-102">Use the Oracle Database Adapter with SharePoint</span></span>
<span data-ttu-id="dfd49-103">WCF 适配器服务开发向导[!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]为 Oracle 数据库和 Oracle E-business Suite Microsoft BizTalk 适配器将直接使用作为 Microsoft SharePoint 中的外部数据源启用 Microsoft BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="dfd49-103">The WCF Adapter Service Development Wizard for [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)] enables the Microsoft BizTalk Adapter for Oracle Database and the Microsoft BizTalk Adapter for Oracle E-Business Suite to be directly consumed as an external datasource in Microsoft SharePoint.</span></span> <span data-ttu-id="dfd49-104">添加服务开发支持此功能启动向导时与**WCF 适配器服务**用于创建新 Visual C# Web 中的站点模板[!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dfd49-104">The Add Service Development Wizard that supports this feature is launched with the **WCF Adapter Service** template for creating a new Visual C# Web Sites in [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="dfd49-105">此模板是附带[!INCLUDE[adapterpacknoversion_md](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dfd49-105">The template is included with the [!INCLUDE[adapterpacknoversion_md](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="dfd49-106">你还必须安装 Microsoft Windows Communication Foundation (WCF) 的业务线 (LOB) 适配器 SDK。</span><span class="sxs-lookup"><span data-stu-id="dfd49-106">You must also install the Microsoft Windows Communication Foundation (WCF) Line of Business (LOB) Adapter SDK.</span></span>  
  
## <a name="sharepoint-operation-support"></a><span data-ttu-id="dfd49-107">SharePoint 操作支持</span><span class="sxs-lookup"><span data-stu-id="dfd49-107">SharePoint Operation Support</span></span>  
 <span data-ttu-id="dfd49-108">适配器服务开发向导将生成适用于 Microsoft SharePoint 的特殊服务协定为 Oracle 适配器。</span><span class="sxs-lookup"><span data-stu-id="dfd49-108">The Adapter Service Development wizard generates a special service contract for the Oracle adapters that is compatible with Microsoft SharePoint.</span></span> <span data-ttu-id="dfd49-109">此向导将生成服务协定，其中包括对与 Microsoft SharePoint 集成适配器执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="dfd49-109">The wizard will generate a service contract which includes the following operations for integrating the adapter with Microsoft SharePoint:</span></span>  
  
-   <span data-ttu-id="dfd49-110">**创建：** CreateItem_ 操作支持。</span><span class="sxs-lookup"><span data-stu-id="dfd49-110">**Create:** Supported by the CreateItem_ operation.</span></span>  
  
-   <span data-ttu-id="dfd49-111">**阅读：** ReadItem_ 操作支持。</span><span class="sxs-lookup"><span data-stu-id="dfd49-111">**Read:** Supported by the ReadItem_ operation.</span></span>  
  
-   <span data-ttu-id="dfd49-112">**更新：** UpdateItem_ 操作支持。</span><span class="sxs-lookup"><span data-stu-id="dfd49-112">**Update:** Supported by the UpdateItem_ operation.</span></span>  
  
-   <span data-ttu-id="dfd49-113">**删除：** DeleteItem_ 操作支持。</span><span class="sxs-lookup"><span data-stu-id="dfd49-113">**Delete:** Supported by the DeleteItem_ operation.</span></span>  
  
-   <span data-ttu-id="dfd49-114">**查询：** ReadList 操作支持。</span><span class="sxs-lookup"><span data-stu-id="dfd49-114">**Query:** Supported by the ReadList operation.</span></span>  
  
-   <span data-ttu-id="dfd49-115">**相关联：** Associate_ 操作支持。</span><span class="sxs-lookup"><span data-stu-id="dfd49-115">**Associate:** Supported by the Associate_ operation.</span></span>  
  
 <span data-ttu-id="dfd49-116">在使用 Microsoft BizTalk 适配器 Oracle 数据库作为的示例生成以下服务协定。</span><span class="sxs-lookup"><span data-stu-id="dfd49-116">The following service contract was generated using for the Microsoft BizTalk Adapter for Oracle Database as an example.</span></span> <span data-ttu-id="dfd49-117">适配器已配置为提供对 EMP 表的访问</span><span class="sxs-lookup"><span data-stu-id="dfd49-117">The adapter is configured to provide access to the EMP table</span></span>  
  
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
  
## <a name="creating-a-new-web-site-to-host-the-microsoft-biztalk-adapter-for-oracle-database-in-iis"></a><span data-ttu-id="dfd49-118">创建新的 Web 站点，以便为在 IIS 中的 Oracle 数据库承载 Microsoft BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="dfd49-118">Creating a New Web Site to Host the Microsoft BizTalk Adapter for Oracle Database in IIS</span></span>  
 <span data-ttu-id="dfd49-119">这些步骤提供了一个示例使用 WCF 适配器服务的开发向导中，若要创建新的 WCF web 服务的 Oracle 数据库承载 Microsoft BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="dfd49-119">These steps provide an example using the WCF Adapter Service Development Wizard, to create a new WCF web service hosting the Microsoft BizTalk Adapter for Oracle Database.</span></span> <span data-ttu-id="dfd49-120">服务协定将包含操作与 Sharepoint 直接兼容。</span><span class="sxs-lookup"><span data-stu-id="dfd49-120">The service contract will include operations directly compatible with Sharepoint.</span></span> <span data-ttu-id="dfd49-121">以便可以直接使用它作为外部数据源。</span><span class="sxs-lookup"><span data-stu-id="dfd49-121">So that it can be directly consumed as an external datasource.</span></span> <span data-ttu-id="dfd49-122">适配器已配置为使用 Oracle 数据库使用进行身份验证**SCOTT**帐户。</span><span class="sxs-lookup"><span data-stu-id="dfd49-122">The adapter is configured to authenticate with the Oracle database using the **SCOTT** account.</span></span> <span data-ttu-id="dfd49-123">如果**SCOTT**锁定帐户，你可以通过以 sysdba 身份登录到 SQL Plus 解锁帐户。</span><span class="sxs-lookup"><span data-stu-id="dfd49-123">If the **SCOTT** account is locked, you can unlock the account by logging into SQL Plus as SYSDBA.</span></span>  
  
```  
<Oracle Installation Bin Directory>\Sqlplus.exe SYS AS SYSDBA  
```  
  
 <span data-ttu-id="dfd49-124">然后运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="dfd49-124">Then run the following command.</span></span>  
  
```  
SQL> ALTER USER scott ACCOUNT UNLOCK;  
```  
  
#### <a name="creating-the-new-web-site-project"></a><span data-ttu-id="dfd49-125">创建新的网站项目</span><span class="sxs-lookup"><span data-stu-id="dfd49-125">Creating the New Web Site Project</span></span>  
  
1.  <span data-ttu-id="dfd49-126">启动**Microsoft [!INCLUDE[vs2012](../../includes/vs2012-md.md)]** 。</span><span class="sxs-lookup"><span data-stu-id="dfd49-126">Start **Microsoft [!INCLUDE[vs2012](../../includes/vs2012-md.md)]**.</span></span>  
  
2.  <span data-ttu-id="dfd49-127">在[!INCLUDE[vs2010](../../includes/vs2010-md.md)]上**文件**菜单上，选择**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="dfd49-127">In [!INCLUDE[vs2010](../../includes/vs2010-md.md)], on the **File** menu, select **New** and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="dfd49-128">在**新项目**对话框框中，展开**其他语言**单击**Visual C#**。</span><span class="sxs-lookup"><span data-stu-id="dfd49-128">In the **New Project** dialog box, expand **Other Languages** and click **Visual C#**.</span></span> <span data-ttu-id="dfd49-129">查找**WCF 适配器服务**在模板列表，然后单击以选中它。</span><span class="sxs-lookup"><span data-stu-id="dfd49-129">Find the **WCF Adapter Service** in the template list and click it to select it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dfd49-130">**WCF 适配器服务**未提供模板如果[!INCLUDE[adapterpackcurrent](../../includes/adapterpackcurrent-md.md)]未安装。</span><span class="sxs-lookup"><span data-stu-id="dfd49-130">The **WCF Adapter Service** template is not available if the [!INCLUDE[adapterpackcurrent](../../includes/adapterpackcurrent-md.md)] is not installed.</span></span> <span data-ttu-id="dfd49-131">在 x64 系统中，安装的 x86 和 x64 版本[!INCLUDE[adapterpackcurrent](../../includes/adapterpackcurrent-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dfd49-131">On x64 systems, install both the x86 and x64 versions of the [!INCLUDE[adapterpackcurrent](../../includes/adapterpackcurrent-md.md)].</span></span>  
  
4.  <span data-ttu-id="dfd49-132">指定**ScottEMP**作为名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="dfd49-132">Specify **ScottEMP** for the name, and then click **OK**.</span></span> <span data-ttu-id="dfd49-133">**WCF 适配器服务开发向导**启动。</span><span class="sxs-lookup"><span data-stu-id="dfd49-133">The **WCF Adapter Service Development Wizard** starts.</span></span>  
  
5.  <span data-ttu-id="dfd49-134">上**简介**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="dfd49-134">On the **Introduction** page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="dfd49-135">上**选择操作**页上，指定**oracleDBBinding**绑定。</span><span class="sxs-lookup"><span data-stu-id="dfd49-135">On the **Choose Operations** page, specify the **oracleDBBinding** binding.</span></span>  
  
7.  <span data-ttu-id="dfd49-136">单击**配置**按钮。</span><span class="sxs-lookup"><span data-stu-id="dfd49-136">Click the **Configure** button.</span></span> <span data-ttu-id="dfd49-137">**配置适配器**显示对话框。</span><span class="sxs-lookup"><span data-stu-id="dfd49-137">The **Configure Adapter** dialog is displayed.</span></span>  
  
8.  <span data-ttu-id="dfd49-138">上**安全**选项卡上，选择**用户名**中**客户端凭据类型**下拉列表框。</span><span class="sxs-lookup"><span data-stu-id="dfd49-138">On the **Security** tab, select **Username** in the **Client credential type** dropdown list box.</span></span>  
  
9. <span data-ttu-id="dfd49-139">输入**SCOTT**用户名称和 SCOTT 帐户输入正确的密码。</span><span class="sxs-lookup"><span data-stu-id="dfd49-139">Enter **SCOTT** for the User name and enter the correct password for the SCOTT account.</span></span> <span data-ttu-id="dfd49-140">SCOTT 帐户的默认密码是**tiger**。</span><span class="sxs-lookup"><span data-stu-id="dfd49-140">The default password for the SCOTT account is **tiger**.</span></span>  
  
10. <span data-ttu-id="dfd49-141">单击**URI 属性**选项卡上，输入中的 Oracle 服务器的 IP 地址或主机名**ServerAddress**框。</span><span class="sxs-lookup"><span data-stu-id="dfd49-141">Click the **URI Properties** tab, enter the IP address or host name for your Oracle server in the **ServerAddress** box.</span></span>  
  
11. <span data-ttu-id="dfd49-142">输入中的正确 Oracle 数据库服务实例名称**ServiceName**框。</span><span class="sxs-lookup"><span data-stu-id="dfd49-142">Enter the correct Oracle database service instance name in the **ServiceName** box.</span></span> <span data-ttu-id="dfd49-143">你可以复制的实例名称信息从 Oracle Enterprise Manager。</span><span class="sxs-lookup"><span data-stu-id="dfd49-143">You can copy the instance name information from Oracle Enterprise Manager.</span></span>  
  
12. <span data-ttu-id="dfd49-144">按**确定**按钮上**配置适配器**对话框</span><span class="sxs-lookup"><span data-stu-id="dfd49-144">Press the **OK** button on the **Configure Adapter** dialog</span></span>  
  
13. <span data-ttu-id="dfd49-145">上**选择操作**页的向导中，单击**连接**按钮并等待几分钟要为 Oracle 数据库生成的类别。</span><span class="sxs-lookup"><span data-stu-id="dfd49-145">On the **Choose Operations** page of the wizard, click the **Connect** button and wait a few moments for the categories to be built for the Oracle database.</span></span>  
  
14. <span data-ttu-id="dfd49-146">将类别添加中后**选择类别**列表中，向下滚动到**SCOTT**并将其展开。</span><span class="sxs-lookup"><span data-stu-id="dfd49-146">Once the categories are added in the **Select a category** list, scroll down to **SCOTT** and expand it.</span></span> <span data-ttu-id="dfd49-147">然后展开**表**单击**EMP**表条目。</span><span class="sxs-lookup"><span data-stu-id="dfd49-147">Then expand **Table** and click the **EMP** table entry.</span></span>  
  
15. <span data-ttu-id="dfd49-148">在**可用类别和操作**列表，在列表中选择的所有操作并单击**添加**按钮。</span><span class="sxs-lookup"><span data-stu-id="dfd49-148">In the **Available categories and operations** list, select all the operations in the list and click the **Add** button.</span></span> <span data-ttu-id="dfd49-149">所有操作都添加到**都添加类别和操作**列表。</span><span class="sxs-lookup"><span data-stu-id="dfd49-149">All the operations are added to the **Added categories and operations** list.</span></span>  
  
16. <span data-ttu-id="dfd49-150">上**选择操作**页上，单击**下一步**按钮。</span><span class="sxs-lookup"><span data-stu-id="dfd49-150">On the **Choose Operations** page, click the **Next** button.</span></span>  
  
17. <span data-ttu-id="dfd49-151">上**配置服务和终结点行为**页上，设置**UseServiceCertificate**服务行为到**false**对于此示例。</span><span class="sxs-lookup"><span data-stu-id="dfd49-151">On the **Configure Service and Endpoint Behaviors** page, set the **UseServiceCertificate** Service behavior to **false** for this example.</span></span> <span data-ttu-id="dfd49-152">然后单击**下一步**按钮。</span><span class="sxs-lookup"><span data-stu-id="dfd49-152">Then click the **Next** button.</span></span>  
  
18. <span data-ttu-id="dfd49-153">上**配置服务终结点绑定和地址**页上，单击**应用**按钮。</span><span class="sxs-lookup"><span data-stu-id="dfd49-153">On the **Configure Service Endpoint Binding and Address** page, click the **Apply** button.</span></span> <span data-ttu-id="dfd49-154">然后单击**下一步**按钮。</span><span class="sxs-lookup"><span data-stu-id="dfd49-154">Then click the **Next** button.</span></span>  
  
19. <span data-ttu-id="dfd49-155">上**摘要**页上，单击**完成**按钮。</span><span class="sxs-lookup"><span data-stu-id="dfd49-155">On the **Summary** page, click the **Finish** button.</span></span>  
  
20. <span data-ttu-id="dfd49-156">单击**生成**菜单选项，然后单击**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="dfd49-156">Click the **Build** menu option and then click **Build Solution**.</span></span> <span data-ttu-id="dfd49-157">验证项目生成成功并且没有错误。</span><span class="sxs-lookup"><span data-stu-id="dfd49-157">Verify the project build was successful with no errors.</span></span>  
  
## <a name="publishing-the-new-service-to-iis"></a><span data-ttu-id="dfd49-158">新的服务发布到 IIS</span><span class="sxs-lookup"><span data-stu-id="dfd49-158">Publishing the New Service to IIS</span></span>  
 <span data-ttu-id="dfd49-159">对于此示例在将发布到本地 IIS web 服务器的适配器主机服务。</span><span class="sxs-lookup"><span data-stu-id="dfd49-159">For this example you will publish the adapter host service to the local IIS web server.</span></span>  
  
1.  <span data-ttu-id="dfd49-160">在解决方案资源管理器[!INCLUDE[vs2010](../../includes/vs2010-md.md)]，右键单击**ScottEmp**项目，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="dfd49-160">In Solution Explorer for [!INCLUDE[vs2010](../../includes/vs2010-md.md)], right click the **ScottEmp** project and click **Properties**.</span></span> <span data-ttu-id="dfd49-161">将显示项目设计器选项卡。</span><span class="sxs-lookup"><span data-stu-id="dfd49-161">The Project Designer tabs are displayed.</span></span>  
  
2.  <span data-ttu-id="dfd49-162">单击**Web**选项卡，然后单击**使用本地 IIS Web 服务器**选项。</span><span class="sxs-lookup"><span data-stu-id="dfd49-162">Click the **Web** tab, then click the **Use Local IIS Web server** option.</span></span>  
  
3.  <span data-ttu-id="dfd49-163">单击**创建虚拟目录**按钮。</span><span class="sxs-lookup"><span data-stu-id="dfd49-163">Click the **Create Virtual Directory** button.</span></span>  
  
4.  <span data-ttu-id="dfd49-164">打开 web 浏览器到服务地址**http://localhost/ScottEmp/ISCOTT_EMP.svc**。</span><span class="sxs-lookup"><span data-stu-id="dfd49-164">Open a web browser to the service address **http://localhost/ScottEmp/ISCOTT_EMP.svc**.</span></span> <span data-ttu-id="dfd49-165">你应该会收到一条消息"你已创建的服务"，该值指示适配器承载于 IIS 中。</span><span class="sxs-lookup"><span data-stu-id="dfd49-165">You should receive a message stating “You have created a service” indicating the adapter is hosted in IIS.</span></span>  
  
## <a name="adding-the-external-data-source-to-a-sharepoint-site-using-sharepoint-designer"></a><span data-ttu-id="dfd49-166">将外部数据源添加到 SharePoint 站点使用 SharePoint Designer</span><span class="sxs-lookup"><span data-stu-id="dfd49-166">Adding the External Data Source to a SharePoint Site using SharePoint Designer</span></span>  
 <span data-ttu-id="dfd49-167">本部分介绍如何将 WCF 服务作为外部数据源添加到新的网站使用 SharePoint Designer。</span><span class="sxs-lookup"><span data-stu-id="dfd49-167">This section describes how to add the WCF Service as an external data source to a new Web Site using SharePoint Designer.</span></span>  
  
#### <a name="adding-the-external-data-source"></a><span data-ttu-id="dfd49-168">添加外部数据源</span><span class="sxs-lookup"><span data-stu-id="dfd49-168">Adding the External Data source</span></span>  
  
1.  <span data-ttu-id="dfd49-169">打开 SharePoint Designer 并创建新网站。</span><span class="sxs-lookup"><span data-stu-id="dfd49-169">Open SharePoint Designer and create a new Web Site.</span></span>  
  
2.  <span data-ttu-id="dfd49-170">在 SharePoint 设计器中，展开**导航**单击**外部内容类型**中**站点对象**列表。</span><span class="sxs-lookup"><span data-stu-id="dfd49-170">In SharePoint Designer, expand **Navigation** and click **External Content types** in the **Site Objects** list.</span></span>  
  
3.  <span data-ttu-id="dfd49-171">单击**外部内容类型**菜单按钮创建新的外部内容类型。</span><span class="sxs-lookup"><span data-stu-id="dfd49-171">Click the **External Content Type** menu button to create a new external content type.</span></span>  
  
4.  <span data-ttu-id="dfd49-172">单击旁边的文本**名称**编辑新的外部内容类型的名称。</span><span class="sxs-lookup"><span data-stu-id="dfd49-172">Click the text beside **Name** to edit the name of the new external content type.</span></span> <span data-ttu-id="dfd49-173">输入**OracleEMP**的名称。</span><span class="sxs-lookup"><span data-stu-id="dfd49-173">Enter **OracleEMP** for the name.</span></span>  
  
5.  <span data-ttu-id="dfd49-174">单击旁边的文本链接**外部系统**表示**单击此处以查看外部数据源和操作。**。</span><span class="sxs-lookup"><span data-stu-id="dfd49-174">Click the text link beside **External System** which says **Click here to discover external data sources and operations.**.</span></span> <span data-ttu-id="dfd49-175">这将打开操作设计器中为 OracleEMP 外部内容类型。</span><span class="sxs-lookup"><span data-stu-id="dfd49-175">This opens the Operation Designer for the OracleEMP external content type.</span></span>  
  
6.  <span data-ttu-id="dfd49-176">单击**添加连接**发现屏幕上的按钮。</span><span class="sxs-lookup"><span data-stu-id="dfd49-176">Click the **Add Connection** button on the discovery screen.</span></span>  
  
7.  <span data-ttu-id="dfd49-177">在外部数据源类型选择对话框中，选择**WCF 服务**单击**确定**按钮。</span><span class="sxs-lookup"><span data-stu-id="dfd49-177">In the External Data Source Type Selection dialog, choose **WCF Service** and click the **OK** button.</span></span>  
  
8.  <span data-ttu-id="dfd49-178">在 WCF 连接对话框中，在**服务元数据 URL**框中输入**https://localhost/ScottEmp/ISCOTT_EMP.svc?wsdl**</span><span class="sxs-lookup"><span data-stu-id="dfd49-178">In the WCF Connection dialog, in the **Service Metadata URL** box enter **https://localhost/ScottEmp/ISCOTT_EMP.svc?wsdl**</span></span>  
  
9. <span data-ttu-id="dfd49-179">在**服务终结点 URL**框中输入**https://localhost/ScottEmp/ISCOTT_EMP.svc**</span><span class="sxs-lookup"><span data-stu-id="dfd49-179">In the **Service Endpoint URL** box enter **https://localhost/ScottEmp/ISCOTT_EMP.svc**</span></span>  
  
10. <span data-ttu-id="dfd49-180">单击**确定**按钮以关闭 WCF 连接对话框。</span><span class="sxs-lookup"><span data-stu-id="dfd49-180">Click the **OK** button to close the WCF Connection dialog.</span></span>  
  
11. <span data-ttu-id="dfd49-181">后填充了数据源信息，则展开**https://localhost/ScottEmp/ISCOTT_EMP.svc**数据源，并展开**Web 方法**。</span><span class="sxs-lookup"><span data-stu-id="dfd49-181">Once the Data Source information is populated, expand the **https://localhost/ScottEmp/ISCOTT_EMP.svc** data source and expand **Web Methods**.</span></span>  
  
12. <span data-ttu-id="dfd49-182">右键单击**ReadList** Web 方法，并单击**新读列表操作**。</span><span class="sxs-lookup"><span data-stu-id="dfd49-182">Right click the **ReadList** Web Method and click **New Read List Operation**.</span></span> <span data-ttu-id="dfd49-183">读取列表配置对话框被启动。</span><span class="sxs-lookup"><span data-stu-id="dfd49-183">The Read List configuration dialog is launched.</span></span>  
  
13. <span data-ttu-id="dfd49-184">在读取列表对话框中单击**返回参数**单击**EMPNO**中数据源元素。</span><span class="sxs-lookup"><span data-stu-id="dfd49-184">In the Read List dialog click **Return Parameters** and click **EMPNO** in the Data Source Elements.</span></span> <span data-ttu-id="dfd49-185">单击**映射到标识符**。</span><span class="sxs-lookup"><span data-stu-id="dfd49-185">Click the **Map to identifier**.</span></span>  
  
14. <span data-ttu-id="dfd49-186">单击**完成**在读取列表对话框中。</span><span class="sxs-lookup"><span data-stu-id="dfd49-186">Click **Finish** in the Read List dialog.</span></span>  
  
15. <span data-ttu-id="dfd49-187">通过键入保存新的外部数据源**Ctrl + s**。</span><span class="sxs-lookup"><span data-stu-id="dfd49-187">Save the new external data source by typing **Ctrl+s**.</span></span>  
  
#### <a name="testing-the-external-data-source-connection"></a><span data-ttu-id="dfd49-188">测试外部数据源连接</span><span class="sxs-lookup"><span data-stu-id="dfd49-188">Testing the External Data Source Connection</span></span>  
  
1.  <span data-ttu-id="dfd49-189">在新的网站上，单击**创建列出和窗体**按钮。</span><span class="sxs-lookup"><span data-stu-id="dfd49-189">In the new web site, click the **Create Lists and Forms** button.</span></span> <span data-ttu-id="dfd49-190">创建列表和窗体 OracleEMP 对话框将出现。</span><span class="sxs-lookup"><span data-stu-id="dfd49-190">The Create List and Form for OracleEMP dialog appears.</span></span>  
  
2.  <span data-ttu-id="dfd49-191">输入**OracleEMP_List**列表名称然后单击**确定**按钮。</span><span class="sxs-lookup"><span data-stu-id="dfd49-191">Enter **OracleEMP_List** for the List Name and click the **OK** button.</span></span>  
  
3.  <span data-ttu-id="dfd49-192">列表是在创建后，单击**摘要视图**菜单上的按钮。</span><span class="sxs-lookup"><span data-stu-id="dfd49-192">Once the list is create, click the **Summary View** button on the menu.</span></span>  
  
4.  <span data-ttu-id="dfd49-193">单击**OracleEMP_List**下外部列表。</span><span class="sxs-lookup"><span data-stu-id="dfd49-193">Click **OracleEMP_List** under External Lists.</span></span>  
  
5.  <span data-ttu-id="dfd49-194">单击**在浏览器中的预览**若要测试的适配器 ReadList 操作菜单上的按钮。</span><span class="sxs-lookup"><span data-stu-id="dfd49-194">Click the **Preview in Browser** button on the menu to test the ReadList operation of the adapter.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="dfd49-195">故障排除</span><span class="sxs-lookup"><span data-stu-id="dfd49-195">Troubleshooting</span></span>  
  
-   <span data-ttu-id="dfd49-196">在 64 位计算机上，你必须确保还安装了 32 位 Oracle 客户端组件。</span><span class="sxs-lookup"><span data-stu-id="dfd49-196">On 64-bit machines you must make sure that 32-bit Oracle client components are also installed.</span></span> <span data-ttu-id="dfd49-197">这是因为[!INCLUDE[vs2010](../../includes/vs2010-md.md)]和将作为在开发过程中需要访问 32 位组件的 32 位进程中运行它的向导。</span><span class="sxs-lookup"><span data-stu-id="dfd49-197">This is because [!INCLUDE[vs2010](../../includes/vs2010-md.md)] and it’s wizards will be running as a 32-bit process requiring access to 32-bit components during development.</span></span>