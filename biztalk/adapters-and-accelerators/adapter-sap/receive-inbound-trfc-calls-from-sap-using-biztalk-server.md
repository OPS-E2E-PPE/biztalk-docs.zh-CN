---
title: 接收来自 SAP 使用 BizTalk Server 的入站的 tRFC 调用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tRFC calls, receiving using BizTalk Server
- tRFCs, sample
ms.assetid: 500eedea-3d27-478c-a64c-903a1fa2b02f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d98d1f38e45109649d64758b74c0ae5fc1489e9c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373040"
---
# <a name="receive-inbound-trfc-calls-from-sap-using-biztalk-server"></a><span data-ttu-id="0a4fd-102">接收来自 SAP 使用 BizTalk Server 的入站的 tRFC 调用</span><span class="sxs-lookup"><span data-stu-id="0a4fd-102">Receive Inbound tRFC Calls from SAP using BizTalk Server</span></span>
<span data-ttu-id="0a4fd-103">TRFC 服务器调用是事务性的 RFC 服务器调用。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-103">A tRFC server call is a transactional RFC server call.</span></span> <span data-ttu-id="0a4fd-104">在事务上下文中接收 RFC 所需的业务流程将类似于业务流程，以接收来自 SAP 系统发送任何其他入站的 RFC。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-104">The orchestration required to receive an RFC in a transactional context is similar to the orchestration to receive any other inbound RFC sent from an SAP system.</span></span> <span data-ttu-id="0a4fd-105">但是，您需要执行某些其他任务以确保 Rfc 接收事务上下文中。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-105">However, you need to perform certain additional tasks to make sure the RFCs are received in a transactional context.</span></span> <span data-ttu-id="0a4fd-106">有关接收来自 SAP 系统使用的入站的 RFC [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，请参阅[SAP 使用 BizTalk Server 接收入站 RFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-106">For more information about receiving an inbound RFC from the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Receive Inbound RFC Calls from SAP by using BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md).</span></span> <span data-ttu-id="0a4fd-107">详细了解如何[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持入站的 tRFC 调用接收来自 SAP 系统，请参阅[Trfc 在 SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-107">For more information about how the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports receiving inbound tRFC calls from an SAP system, see [Operations on tRFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span></span>  
  
 <span data-ttu-id="0a4fd-108">接收来自 SAP 系统发送入站的 tRFC 是类似于接收的入站的 RFC，具有以下差异：</span><span class="sxs-lookup"><span data-stu-id="0a4fd-108">Receiving an inbound tRFC sent from an SAP system is similar to receiving an inbound RFC, with the following differences:</span></span>  
  
1. <span data-ttu-id="0a4fd-109">在设计时，生成架构时请确保您选择从下的 tRFC **TRFC**节点。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-109">At design time, while generating the schema, make sure you select the tRFC from under the **TRFC** node.</span></span>  
  
2. <span data-ttu-id="0a4fd-110">在运行时，请确保设置的绑定属性**TidDatabaseConnectionString**。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-110">At run time, make sure you set the binding property **TidDatabaseConnectionString**.</span></span> <span data-ttu-id="0a4fd-111">此属性使用连接字符串以连接到 SQL 数据库来存储 TID。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-111">This property takes the connection string to connect to a SQL database to store the TID.</span></span> <span data-ttu-id="0a4fd-112">一个连接字符串示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="0a4fd-112">A sample connection string would look like:</span></span>  
  
   ```  
   Data Source=<myServerAddress>;Initial Catalog=<myDataBase>;User Id=<myUsername>;Password=<myPassword>;  
   ```  
  
    <span data-ttu-id="0a4fd-113">有关绑定属性以及如何将其设置的详细信息，请参阅[了解用于 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-113">For more information about the binding property and how to set it, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="0a4fd-114">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装向导安装 SQL 脚本，SapAdapter-DbScript-Install.sql，必须运行由 SQL Server 管理员在 SQL Server 中创建数据库和数据库对象。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-114">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup wizard installs a SQL script, SapAdapter-DbScript-Install.sql, which must be run by the SQL Server administrator to create a database and the database objects in SQL Server.</span></span> <span data-ttu-id="0a4fd-115">该脚本通常安装在 *\<安装驱动器\>： 程序 FilesMicrosoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]* 。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-115">The script is typically installed at *\<installation drive\>:Program FilesMicrosoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]*.</span></span>  
   > 
   >  <span data-ttu-id="0a4fd-116">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]这些对象用于持久保存 Tid。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-116">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses these objects to persist the TIDs.</span></span> <span data-ttu-id="0a4fd-117">因此，SQL Server 管理员必须确保用户名称提供，如连接字符串的一部分具有足够权限来执行存储的过程。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-117">So, the SQL Server administrator must ensure that the user name provide as part of the connection string has sufficient privileges to execute the stored procedures.</span></span> <span data-ttu-id="0a4fd-118">如果 Windows 用户有足够的权限在数据库中执行存储的过程，也可以选择 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-118">You can also opt for Windows authentication provided the Windows user has sufficient permissions to execute stored procedures in the database.</span></span>  
  
3. <span data-ttu-id="0a4fd-119">请确保安装了适配器的计算机上启用 MSDTC。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-119">Make sure MSDTC is enabled on the computer where the adapter is installed.</span></span> <span data-ttu-id="0a4fd-120">执行以下步骤启用 MSDTC。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-120">Perform the following steps to enable MSDTC.</span></span>  
  
   1.  <span data-ttu-id="0a4fd-121">启动组件服务 MMC 管理单元。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-121">Start the Component Services MMC snap-in.</span></span>  
  
   2.  <span data-ttu-id="0a4fd-122">在组件服务 MMC 管理单元中，在左窗格中展开**组件服务**，展开**计算机**，右键单击**我的电脑**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-122">In the Component Services MMC snap-in, from the left pane expand **Component Services**, expand **Computers**, right-click **My Computer**, and click **Properties**.</span></span>  
  
   3.  <span data-ttu-id="0a4fd-123">在中**我的电脑属性**对话框中，单击**MSDTC**选项卡。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-123">In the **My Computer Properties** dialog box, click the **MSDTC** tab.</span></span>  
  
   4.  <span data-ttu-id="0a4fd-124">在中**事务配置**部分中，单击**的安全配置**按钮。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-124">In the **Transaction Configuration** section, click the **Security Configuration** button.</span></span>  
  
   5.  <span data-ttu-id="0a4fd-125">在中**的安全配置**对话框中，选择**网络 DTC 访问**复选框，然后在其中选择**允许远程客户端**复选框。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-125">In the **Security Configuration** dialog box, select the **Network DTC Access** check box and within that, select the **Allow Remote Clients** check box.</span></span>  
  
   6.  <span data-ttu-id="0a4fd-126">在中**事务管理器通信**部分中，选择**允许入站**并**允许出站**复选框。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-126">In the **Transaction Manager Communication** section, select the **Allow Inbound** and **Allow Outbound** check boxes.</span></span>  
  
   7.  <span data-ttu-id="0a4fd-127">在中**的安全配置**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-127">In the **Security Configuration** dialog box, click **OK**.</span></span>  
  
   8.  <span data-ttu-id="0a4fd-128">单击**是**通知 MSDTC 服务将重新启动对话框框中。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-128">Click **Yes** in the dialog box informing that the MSDTC service will be restarted.</span></span> <span data-ttu-id="0a4fd-129">重新启动 MSDTC 服务后，单击**确定**对话框上。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-129">After the MSDTC service is restarted, click **OK** on the dialog box.</span></span>  
  
   9. <span data-ttu-id="0a4fd-130">在中**我的电脑属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-130">In the **My Computer Properties** dialog box, click **OK**.</span></span>  
  
4. <span data-ttu-id="0a4fd-131">将 MSDTC 添加到 Windows 防火墙例外列表中，如果不是已添加。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-131">Add MSDTC to the Windows Firewall exception list, if not already added.</span></span> <span data-ttu-id="0a4fd-132">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-132">Run the following command.</span></span>  
  
   ```  
   netsh firewall set allowedprogram %windir%\system32\msdtc.exe MSDTC enable  
   ```  
  
> [!IMPORTANT]
>  <span data-ttu-id="0a4fd-133">从"事务性"上下文中的 SAP 系统接收 Idoc 时使用的入站的 tRFC 调用。</span><span class="sxs-lookup"><span data-stu-id="0a4fd-133">An inbound tRFC call is used while receiving IDOCs from the SAP system in a "transactional" context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a4fd-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a4fd-134">See Also</span></span>  
[<span data-ttu-id="0a4fd-135">开发 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="0a4fd-135">Develop BizTalk applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)