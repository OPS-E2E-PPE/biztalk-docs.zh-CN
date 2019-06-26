---
title: 接收来自事务性上下文中使用 BizTalk Server 中的 SAP 的 Idoc |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transactional context
- IDOCs, receiving in a transactional context using BizTalk Server
ms.assetid: 6a01bb82-7292-4b70-8ad7-996d389a9365
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3781d2088c56b5dbd0b1b502e46c04537c836b37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373067"
---
# <a name="receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server"></a><span data-ttu-id="9eef5-102">接收来自事务性上下文中使用 BizTalk Server 中的 SAP 的 Idoc</span><span class="sxs-lookup"><span data-stu-id="9eef5-102">Receive IDOCs from SAP in a Transactional Context using BizTalk Server</span></span>
<span data-ttu-id="9eef5-103">在事务性上下文中接收 IDOC 是类似于在事务上下文中接收 Trfc。</span><span class="sxs-lookup"><span data-stu-id="9eef5-103">Receiving IDOC in a transactional context is similar to receiving tRFCs in a transactional context.</span></span> <span data-ttu-id="9eef5-104">在这种情况下，SAP 系统从收到的 IDOC 所包含的作为的一部分的 TID *\<TransactionalRfcOperationIdentifier\>* 元素。</span><span class="sxs-lookup"><span data-stu-id="9eef5-104">In such a case, the IDOC received from the SAP system contains a TID as part of the *\<TransactionalRfcOperationIdentifier\>* element.</span></span> <span data-ttu-id="9eef5-105">此 TID 适配器保存在 SQL 数据库中。</span><span class="sxs-lookup"><span data-stu-id="9eef5-105">This TID is persisted in a SQL database by the adapter.</span></span> <span data-ttu-id="9eef5-106">如果发送 IDOC 的 SAP 系统中的 ABAP 代码具有"COMMIT WORK"语句，响应发送到 SAP 系统后是从 SQL 数据库中删除 TID。</span><span class="sxs-lookup"><span data-stu-id="9eef5-106">If the ABAP code in the SAP system that sends the IDOC has a "COMMIT WORK" statement, the TID is deleted from the SQL database after a response is sent back to the SAP system.</span></span>  
  
 <span data-ttu-id="9eef5-107">不管是否收到了 IDOC 事务上下文中或不类似，才能接收 IDOC 的业务流程。</span><span class="sxs-lookup"><span data-stu-id="9eef5-107">The orchestration required to receive an IDOC is similar irrespective of whether the IDOC is received in a transactional context or not.</span></span> <span data-ttu-id="9eef5-108">请参阅[通过使用 BizTalk Server 接收来自 SAP 的 Idoc](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="9eef5-108">See [Receive IDOCs from SAP by Using BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md).</span></span> <span data-ttu-id="9eef5-109">但是，您需要执行某些其他任务以确保在事务上下文中接收 Idoc。</span><span class="sxs-lookup"><span data-stu-id="9eef5-109">However, you need to perform certain additional tasks to make sure the IDOCs are received in a transactional context.</span></span>  
  
1. <span data-ttu-id="9eef5-110">在设计时，生成你想要收到的 IDOC 的架构。</span><span class="sxs-lookup"><span data-stu-id="9eef5-110">At design time, generate the schema for an IDOC that you want to receive.</span></span>  
  
2. <span data-ttu-id="9eef5-111">在运行时，请确保设置的绑定属性**TidDatabaseConnectionString**。</span><span class="sxs-lookup"><span data-stu-id="9eef5-111">At run time, make sure you set the binding property **TidDatabaseConnectionString**.</span></span> <span data-ttu-id="9eef5-112">此属性使用连接字符串以连接到 SQL 数据库来存储 TID。</span><span class="sxs-lookup"><span data-stu-id="9eef5-112">This property takes the connection string to connect to a SQL database to store the TID.</span></span> <span data-ttu-id="9eef5-113">一个连接字符串示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="9eef5-113">A sample connection string would look like:</span></span>  
  
   ```  
   Data Source=<myServerAddress>;Initial Catalog=<myDataBase>;User Id=<myUsername>;Password=<myPassword>;  
   ```  
  
    <span data-ttu-id="9eef5-114">有关绑定属性以及如何将其设置的详细信息，请参阅[了解用于 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="9eef5-114">For more information about the binding property and how to set it, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="9eef5-115">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装向导安装 SQL 脚本，SapAdapter-DbScript-Install.sql，必须运行由 SQL Server 管理员在 SQL Server 中创建数据库和数据库对象。</span><span class="sxs-lookup"><span data-stu-id="9eef5-115">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup wizard installs a SQL script, SapAdapter-DbScript-Install.sql, which must be run by the SQL Server administrator to create a database and the database objects in SQL Server.</span></span> <span data-ttu-id="9eef5-116">该脚本通常安装在 *\<安装驱动器\>* ： 程序 FilesMicrosoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9eef5-116">The script is typically installed at *\<installation drive\>*:Program FilesMicrosoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span>  
   > 
   >  <span data-ttu-id="9eef5-117">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]这些对象用于持久保存 Tid。</span><span class="sxs-lookup"><span data-stu-id="9eef5-117">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses these objects to persist the TIDs.</span></span> <span data-ttu-id="9eef5-118">因此，SQL Server 管理员必须确保用户名称提供，如连接字符串的一部分具有足够权限来执行存储的过程。</span><span class="sxs-lookup"><span data-stu-id="9eef5-118">So, the SQL Server administrator must ensure that the user name provide as part of the connection string has sufficient privileges to execute the stored procedures.</span></span> <span data-ttu-id="9eef5-119">如果 Windows 用户有足够的权限在数据库中执行存储的过程，也可以选择 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="9eef5-119">You can also opt for Windows authentication provided the Windows user has sufficient permissions to execute stored procedures in the database.</span></span>  
  
3. <span data-ttu-id="9eef5-120">请确保安装了适配器的计算机上启用 MSDTC。</span><span class="sxs-lookup"><span data-stu-id="9eef5-120">Make sure MSDTC is enabled on the computer where the adapter is installed.</span></span> <span data-ttu-id="9eef5-121">执行以下步骤启用 MSDTC。</span><span class="sxs-lookup"><span data-stu-id="9eef5-121">Perform the following steps to enable MSDTC.</span></span>  
  
   1.  <span data-ttu-id="9eef5-122">启动组件服务 MMC 管理单元。</span><span class="sxs-lookup"><span data-stu-id="9eef5-122">Start the Component Services MMC snap-in.</span></span>  
  
   2.  <span data-ttu-id="9eef5-123">在组件服务 MMC 管理单元中，在左窗格中展开**组件服务**，展开**计算机**，右键单击**我的电脑**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="9eef5-123">In the Component Services MMC snap-in, from the left pane expand **Component Services**, expand **Computers**, right-click **My Computer**, and click **Properties**.</span></span>  
  
   3.  <span data-ttu-id="9eef5-124">在中**我的电脑属性**对话框中，单击**MSDTC**选项卡。</span><span class="sxs-lookup"><span data-stu-id="9eef5-124">In the **My Computer Properties** dialog box, click the **MSDTC** tab.</span></span>  
  
   4.  <span data-ttu-id="9eef5-125">在中**事务配置**部分中，单击**的安全配置**按钮。</span><span class="sxs-lookup"><span data-stu-id="9eef5-125">In the **Transaction Configuration** section, click the **Security Configuration** button.</span></span>  
  
   5.  <span data-ttu-id="9eef5-126">在中**的安全配置**对话框中，选择**网络 DTC 访问**复选框，然后在其中选择**允许远程客户端**复选框。</span><span class="sxs-lookup"><span data-stu-id="9eef5-126">In the **Security Configuration** dialog box, select the **Network DTC Access** check box and within that, select the **Allow Remote Clients** check box.</span></span>  
  
   6.  <span data-ttu-id="9eef5-127">在中**事务管理器通信**部分中，选择**允许入站**并**允许出站**复选框。</span><span class="sxs-lookup"><span data-stu-id="9eef5-127">In the **Transaction Manager Communication** section, select the **Allow Inbound** and **Allow Outbound** check boxes.</span></span>  
  
   7.  <span data-ttu-id="9eef5-128">在中**的安全配置**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9eef5-128">In the **Security Configuration** dialog box, click **OK**.</span></span>  
  
   8.  <span data-ttu-id="9eef5-129">单击**是**通知 MSDTC 服务将重新启动对话框框中。</span><span class="sxs-lookup"><span data-stu-id="9eef5-129">Click **Yes** in the dialog box informing that the MSDTC service will be restarted.</span></span> <span data-ttu-id="9eef5-130">重新启动 MSDTC 服务后，单击**确定**对话框上。</span><span class="sxs-lookup"><span data-stu-id="9eef5-130">After the MSDTC service is restarted, click **OK** on the dialog box.</span></span>  
  
   9. <span data-ttu-id="9eef5-131">在中**我的电脑属性**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9eef5-131">In the **My Computer Properties** dialog box, click **OK**.</span></span>  
  
4. <span data-ttu-id="9eef5-132">将 MSDTC 添加到 Windows 防火墙例外列表中，如果不是已添加。</span><span class="sxs-lookup"><span data-stu-id="9eef5-132">Add MSDTC to the Windows Firewall exception list, if not already added.</span></span> <span data-ttu-id="9eef5-133">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="9eef5-133">Run the following command.</span></span>  
  
   ```  
   netsh firewall set allowedprogram %windir%\system32\msdtc.exe MSDTC enable  
   ```  
  
## <a name="see-also"></a><span data-ttu-id="9eef5-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="9eef5-134">See Also</span></span>  
[<span data-ttu-id="9eef5-135">开发 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="9eef5-135">Develop BizTalk applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)