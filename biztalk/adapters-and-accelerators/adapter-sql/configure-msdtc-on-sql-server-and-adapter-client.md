---
title: SQL Server 和适配器客户端上配置 MSDTC |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2c87f455-a8c4-4169-bf18-695926136df1
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4728bd2a0228bcd01b469ec9436d1e3d3dcd257
ms.sourcegitcommit: 2d39bcd10a22c5945d97a03988ccdc62f6fb3c93
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2019
ms.locfileid: "54443378"
---
# <a name="configure-msdtc-on-sql-server-and-adapter-client"></a><span data-ttu-id="7c42e-102">SQL Server 和适配器客户端上配置 MSDTC</span><span class="sxs-lookup"><span data-stu-id="7c42e-102">Configure MSDTC on SQL Server and adapter client</span></span>

<span data-ttu-id="7c42e-103">使用 SQL Server 上执行的操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] (通过[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，WCF 服务模型或 WCF 通道模型) 可以在事务范围内执行。</span><span class="sxs-lookup"><span data-stu-id="7c42e-103">The operations performed on SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] (through [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the WCF service model, or the WCF channel model) can be performed within a transaction scope.</span></span> <span data-ttu-id="7c42e-104">如果客户端程序具有多个事务的资源作为同一事务的一部分，获取提升为 MSDTC 事务的事务。</span><span class="sxs-lookup"><span data-stu-id="7c42e-104">If the client program has more than one transactional resource as part of the same transaction, the transaction gets elevated to an MSDTC transaction.</span></span> <span data-ttu-id="7c42e-105">若要启用要执行操作的作用域内的 MSDTC 事务的适配器，必须配置 MSDTC 这两个运行的计算机上[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]和 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="7c42e-105">To enable the adapter to perform operations within the scope of an MSDTC transaction, you must configure MSDTC both on the computer running the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] and SQL Server.</span></span> <span data-ttu-id="7c42e-106">此外，必须将 MSDTC 添加到 Windows 防火墙例外列表。</span><span class="sxs-lookup"><span data-stu-id="7c42e-106">Also, you must add MSDTC to the exceptions list of Windows Firewall.</span></span> <span data-ttu-id="7c42e-107">本部分提供有关如何运行适配器客户端和 SQL Server 的计算机上执行这些任务的信息。</span><span class="sxs-lookup"><span data-stu-id="7c42e-107">This section provides information about how to perform these tasks on computers running the adapter client and SQL Server.</span></span>  
  
> [!NOTE]
>  - <span data-ttu-id="7c42e-108">在使用 SQL Server 上执行操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]总是涉及到两个资源，连接到 SQL Server 和 BizTalk 消息框驻留在 SQL Server 上的适配器。</span><span class="sxs-lookup"><span data-stu-id="7c42e-108">Performing operations on SQL Server using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] always involves two resources—the adapter connecting to SQL Server and the BizTalk Message Box residing on SQL Server.</span></span> <span data-ttu-id="7c42e-109">因此，所有操作都执行使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]MSDTC 事务的作用域内都执行。</span><span class="sxs-lookup"><span data-stu-id="7c42e-109">Hence, all operations performed using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] are performed within the scope of an MSDTC transaction.</span></span> <span data-ttu-id="7c42e-110">因此，若要使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，始终必须先启用 MSDTC。</span><span class="sxs-lookup"><span data-stu-id="7c42e-110">So, to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you must always enable MSDTC.</span></span>  
> 
>  - <span data-ttu-id="7c42e-111">对于其中适配器客户端不会写入任何数据的 SQL Server 数据库，如 Select 操作的操作可能不希望执行的操作在事务内的额外开销。</span><span class="sxs-lookup"><span data-stu-id="7c42e-111">For operations where the adapter client does not write any data to the SQL Server database, such as a Select operation, you might not want the additional overhead of performing the operations inside a transaction.</span></span> <span data-ttu-id="7c42e-112">在这种情况下，你可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]来执行操作而无需事务性上下文中的设置**UseAmbientTransaction**属性绑定到**false**。</span><span class="sxs-lookup"><span data-stu-id="7c42e-112">In such cases, you can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to perform operations without a transactional context by setting the **UseAmbientTransaction** binding property to **false**.</span></span> <span data-ttu-id="7c42e-113">有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="7c42e-113">For more information about the binding property, see [Read about the BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="7c42e-114">在这种情况下，不需要也配置 MSDTC。</span><span class="sxs-lookup"><span data-stu-id="7c42e-114">In such cases, you do not need to configure MSDTC as well.</span></span>  
  
## <a name="configure-msdtc"></a><span data-ttu-id="7c42e-115">配置 MSDTC</span><span class="sxs-lookup"><span data-stu-id="7c42e-115">Configure MSDTC</span></span>  
  
1. <span data-ttu-id="7c42e-116">打开**组件服务**。</span><span class="sxs-lookup"><span data-stu-id="7c42e-116">Open **Component Services**.</span></span>  

   <span data-ttu-id="7c42e-117">或者，在**服务器管理器**，选择**工具**，然后选择**组件服务**。</span><span class="sxs-lookup"><span data-stu-id="7c42e-117">Or, In **Server Manager**, select **Tools**, and then select **Component Services**.</span></span>  
  
2. <span data-ttu-id="7c42e-118">展开**组件服务**，展开**计算机**，展开**我的电脑**，展开**分布式事务处理协调器**，右键单击**本地 DTC**，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="7c42e-118">Expand **Component Services**, expand **Computers**, expand **My Computer**, expand **Distributed Transaction Coordinator**, right-click **Local DTC**, and select **Properties**.</span></span>  
  
3. <span data-ttu-id="7c42e-119">选择 **“安全”** 选项卡。在此选项卡上，选择以下所有内容的：</span><span class="sxs-lookup"><span data-stu-id="7c42e-119">Select the **Security** tab. In this tab, select all of the following:</span></span> 

   - <span data-ttu-id="7c42e-120">**网络 DTC 访问**</span><span class="sxs-lookup"><span data-stu-id="7c42e-120">**Network DTC Access**</span></span>
   - <span data-ttu-id="7c42e-121">**允许远程客户端**</span><span class="sxs-lookup"><span data-stu-id="7c42e-121">**Allow Remote Clients**</span></span> 
   - <span data-ttu-id="7c42e-122">**允许入站**</span><span class="sxs-lookup"><span data-stu-id="7c42e-122">**Allow Inbound**</span></span> 
   - <span data-ttu-id="7c42e-123">**允许出站**</span><span class="sxs-lookup"><span data-stu-id="7c42e-123">**Allow Outbound**</span></span> 
   - <span data-ttu-id="7c42e-124">**不要求进行验证**</span><span class="sxs-lookup"><span data-stu-id="7c42e-124">**No Authentication Required**</span></span>
  
4. <span data-ttu-id="7c42e-125">单击“确定”保存更改。</span><span class="sxs-lookup"><span data-stu-id="7c42e-125">Select **OK** to save your changes.</span></span>  
  
5. <span data-ttu-id="7c42e-126">如果系统提示重新启动 MSDTC 服务，请选择**是**。</span><span class="sxs-lookup"><span data-stu-id="7c42e-126">If prompted to restart the MSDTC service, select **Yes**.</span></span> <span data-ttu-id="7c42e-127">重新启动 MSDTC 服务后，关闭属性和组件服务 MMC。</span><span class="sxs-lookup"><span data-stu-id="7c42e-127">After the MSDTC service is restarted, close the properties and the Component Services MMC.</span></span> 
  
## <a name="add-msdtc-to-windows-firewall-exceptions-list"></a><span data-ttu-id="7c42e-128">将 MSDTC 添加到 Windows 防火墙例外列表</span><span class="sxs-lookup"><span data-stu-id="7c42e-128">Add MSDTC to Windows Firewall exceptions list</span></span>  

> [!TIP] 
>  <span data-ttu-id="7c42e-129">Microsoft 分布式 Tansaction 处理协调器 (MSDTC) 可能已在防火墙中允许。</span><span class="sxs-lookup"><span data-stu-id="7c42e-129">Microsoft Distributed Tansaction Coordinator (MSDTC) may already be allowed in your firewall.</span></span> <span data-ttu-id="7c42e-130">如果是这样，则将它列出为入站规则。</span><span class="sxs-lookup"><span data-stu-id="7c42e-130">If so, it is listed as an Inbound Rule.</span></span> <span data-ttu-id="7c42e-131">如果未列出，请使用本部分以允许 MSDTC。</span><span class="sxs-lookup"><span data-stu-id="7c42e-131">If it's not listed, use this section to allow MSDTC.</span></span> 

1.  <span data-ttu-id="7c42e-132">打开**Windows 防火墙**，然后选择**高级设置**左侧。</span><span class="sxs-lookup"><span data-stu-id="7c42e-132">Open **Windows Firewall**, and select **Advanced Settings** on the left.</span></span>  

    <span data-ttu-id="7c42e-133">或者，在**服务器管理器**，选择**工具**，然后选择**高级安全 Windows 防火墙**。</span><span class="sxs-lookup"><span data-stu-id="7c42e-133">Or, In **Server Manager**, select **Tools**, and then select **Windows Firewall with Advanced Security**.</span></span>  
  
2.  <span data-ttu-id="7c42e-134">右键单击**入站规则**，然后选择**新规则**。</span><span class="sxs-lookup"><span data-stu-id="7c42e-134">Right click **Inbound Rules**, and select **New Rule**.</span></span>  
  
3.  <span data-ttu-id="7c42e-135">在向导中：</span><span class="sxs-lookup"><span data-stu-id="7c42e-135">In the wizard:</span></span> 

    1. <span data-ttu-id="7c42e-136">选择**程序**，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7c42e-136">Select **Program**, and select **Next**.</span></span> 
    2. <span data-ttu-id="7c42e-137">设置**程序路径**到`%SystemRoot%\system32\msdtc.exe`，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7c42e-137">Set the **program path** to `%SystemRoot%\system32\msdtc.exe`, and select **Next**.</span></span>  
    3. <span data-ttu-id="7c42e-138">**允许连接**，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7c42e-138">**Allow the connection**, and select **Next**.</span></span>
    4. <span data-ttu-id="7c42e-139">选择**域**，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7c42e-139">Select **Domain**, and select **Next**.</span></span>
    5. <span data-ttu-id="7c42e-140">输入任何名称，例如`MSDTC for Oracle EBS`，然后选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="7c42e-140">Enter any name, such as `MSDTC for Oracle EBS`, and select **Finish**.</span></span>
  
5.  <span data-ttu-id="7c42e-141">完成向导，并关闭 Windows 防火墙。</span><span class="sxs-lookup"><span data-stu-id="7c42e-141">Complete the wizard, and close Windows Firewall.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7c42e-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="7c42e-142">See Also</span></span>  
[<span data-ttu-id="7c42e-143">开发 SQL 应用程序</span><span class="sxs-lookup"><span data-stu-id="7c42e-143">Develop your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)
