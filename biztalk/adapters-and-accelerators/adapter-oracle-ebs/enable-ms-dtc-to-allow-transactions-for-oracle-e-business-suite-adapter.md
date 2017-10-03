---
title: "启用 MS 分布式事务处理协调器，以允许 Oracle E-business Suite 的事务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 634538e5-7292-4b3f-85b0-c6db86d0dbd2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0597c050e1531d71a62af04fe6c825653076297c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="enable-ms-distributed-transaction-coordinator-to-allow-transactions-for-oracle-e-business-suite"></a><span data-ttu-id="4ae76-102">启用 MS 分布式事务处理协调器，以允许 Oracle E-business Suite 的事务</span><span class="sxs-lookup"><span data-stu-id="4ae76-102">Enable MS distributed transaction coordinator to allow transactions for Oracle E-Business Suite</span></span>
<span data-ttu-id="4ae76-103">在开始创建应用程序使用之前配置 MSDTC [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4ae76-103">Configure MSDTC before you start creating applications that use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
<span data-ttu-id="4ae76-104">Oracle E-business Suite 使用执行的操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)](通过[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，WCF 服务模型或 WCF 通道模型) 可以在事务范围内执行。</span><span class="sxs-lookup"><span data-stu-id="4ae76-104">The operations performed on Oracle E-Business Suite using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] (through [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the WCF service model, or the WCF channel model) can be performed within a transaction scope.</span></span> <span data-ttu-id="4ae76-105">如果客户端程序具有多个事务的资源在同一事务的一部分，获取提升为 MSDTC 事务的事务。</span><span class="sxs-lookup"><span data-stu-id="4ae76-105">If the client program has more than one transactional resource as part of the same transaction, the transaction gets elevated to an MSDTC transaction.</span></span> <span data-ttu-id="4ae76-106">若要启用的适配器执行 MSDTC 事务的范围内的操作，在运行的计算机上配置 MSDTC [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，和上 Oracle E-business Suite。</span><span class="sxs-lookup"><span data-stu-id="4ae76-106">To enable the adapter to perform operations within the scope of an MSDTC transaction, configure MSDTC on the computer running the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], and on the Oracle E-Business Suite.</span></span> <span data-ttu-id="4ae76-107">此外，添加 MSDTC 到例外列表中你的防火墙，这可能会内置的 Windows 防火墙。</span><span class="sxs-lookup"><span data-stu-id="4ae76-107">Also, add MSDTC to the exceptions list in your firewall, which may be the built-in Windows Firewall.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="4ae76-108">配置 MSDTC 的步骤因个不同的操作系统而异。</span><span class="sxs-lookup"><span data-stu-id="4ae76-108">The steps to configure MSDTC vary for different operating systems.</span></span> <span data-ttu-id="4ae76-109">本主题中列出的步骤适用于 Windows 客户端和 Windows Server 操作系统。</span><span class="sxs-lookup"><span data-stu-id="4ae76-109">The steps listed in this topic apply to Windows client and Windows Server operating systems.</span></span>  
  
## <a name="configure-msdtc"></a><span data-ttu-id="4ae76-110">配置 MSDTC</span><span class="sxs-lookup"><span data-stu-id="4ae76-110">Configure MSDTC</span></span>  
  
1.  <span data-ttu-id="4ae76-111">打开**组件服务**。</span><span class="sxs-lookup"><span data-stu-id="4ae76-111">Open **Component Services**.</span></span>  

    <span data-ttu-id="4ae76-112">或者，在**服务器管理器**，选择**工具**，然后选择**组件服务**。</span><span class="sxs-lookup"><span data-stu-id="4ae76-112">Or, In **Server Manager**, select **Tools**, and then select **Component Services**.</span></span>  
  
2.  <span data-ttu-id="4ae76-113">展开**组件服务**，展开**计算机**，展开**我的电脑**，展开**分布式事务处理协调器**，右键单击**本地 DTC**，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="4ae76-113">Expand **Component Services**, expand **Computers**, expand **My Computer**, expand **Distributed Transaction Coordinator**, right-click **Local DTC**, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="4ae76-114">选择 **“安全”** 选项卡。在此选项卡上，选择如下：</span><span class="sxs-lookup"><span data-stu-id="4ae76-114">Select the **Security** tab. In this tab, select all of the following:</span></span> 

  - <span data-ttu-id="4ae76-115">**网络 DTC 访问**</span><span class="sxs-lookup"><span data-stu-id="4ae76-115">**Network DTC Access**</span></span>
  - <span data-ttu-id="4ae76-116">**允许远程客户端**</span><span class="sxs-lookup"><span data-stu-id="4ae76-116">**Allow Remote Clients**</span></span> 
  - <span data-ttu-id="4ae76-117">**允许入站**</span><span class="sxs-lookup"><span data-stu-id="4ae76-117">**Allow Inbound**</span></span> 
  - <span data-ttu-id="4ae76-118">**允许出站**</span><span class="sxs-lookup"><span data-stu-id="4ae76-118">**Allow Outbound**</span></span> 
  - <span data-ttu-id="4ae76-119">**所需的任何 Authetnication**</span><span class="sxs-lookup"><span data-stu-id="4ae76-119">**No Authetnication Required**</span></span>
  
4.  <span data-ttu-id="4ae76-120">单击“确定”保存更改。</span><span class="sxs-lookup"><span data-stu-id="4ae76-120">Select **OK** to save your changes.</span></span>  
  
5.  <span data-ttu-id="4ae76-121">如果系统提示您重新启动 MSDTC 服务，选择**是**。</span><span class="sxs-lookup"><span data-stu-id="4ae76-121">If prompted to restarted the MSDTC service, select **Yes**.</span></span> <span data-ttu-id="4ae76-122">重新启动 MSDTC 服务后，关闭属性和组件服务 MMC。</span><span class="sxs-lookup"><span data-stu-id="4ae76-122">After the MSDTC service is restarted, close the properties and the Component Services MMC.</span></span> 
  
## <a name="add-msdtc-to-windows-firewall-exceptions-list"></a><span data-ttu-id="4ae76-123">将 MSDTC 添加到 Windows 防火墙例外列表</span><span class="sxs-lookup"><span data-stu-id="4ae76-123">Add MSDTC to Windows Firewall exceptions list</span></span>  

> [!TIP] 
>  <span data-ttu-id="4ae76-124">Microsoft 分布式 Tansaction 处理协调器 (MSDTC) 可能已允许在防火墙中。</span><span class="sxs-lookup"><span data-stu-id="4ae76-124">Microsoft Distributed Tansaction Coordinator (MSDTC) may already be allowed in your firewall.</span></span> <span data-ttu-id="4ae76-125">如果是这样，则将它列出为入站规则。</span><span class="sxs-lookup"><span data-stu-id="4ae76-125">If so, it is listed as an Inbound Rule.</span></span> <span data-ttu-id="4ae76-126">如果未列出，请使用本部分以允许 MSDTC。</span><span class="sxs-lookup"><span data-stu-id="4ae76-126">If it's not listed, use this section to allow MSDTC.</span></span> 

1.  <span data-ttu-id="4ae76-127">打开**Windows 防火墙**，然后选择**高级设置**左侧。</span><span class="sxs-lookup"><span data-stu-id="4ae76-127">Open **Windows Firewall**, and select **Advanced Settings** on the left.</span></span>  

    <span data-ttu-id="4ae76-128">或者，在**服务器管理器**，选择**工具**，然后选择**高级安全 Windows 防火墙**。</span><span class="sxs-lookup"><span data-stu-id="4ae76-128">Or, In **Server Manager**, select **Tools**, and then select **Windows Firewall with Advanced Security**.</span></span>  
  
2.  <span data-ttu-id="4ae76-129">右键单击**入站规则**，然后选择**新规则**。</span><span class="sxs-lookup"><span data-stu-id="4ae76-129">Right click **Inbound Rules**, and select **New Rule**.</span></span>  
  
3.  <span data-ttu-id="4ae76-130">在向导中：</span><span class="sxs-lookup"><span data-stu-id="4ae76-130">In the wizard:</span></span> 

    1. <span data-ttu-id="4ae76-131">选择**程序**，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4ae76-131">Select **Program**, and select **Next**.</span></span> 
    2. <span data-ttu-id="4ae76-132">设置**程序路径**到`%SystemRoot%\system32\msdtc.exe`，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4ae76-132">Set the **program path** to `%SystemRoot%\system32\msdtc.exe`, and select **Next**.</span></span>  
    3. <span data-ttu-id="4ae76-133">**允许连接**，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4ae76-133">**Allow the connection**, and select **Next**.</span></span>
    4. <span data-ttu-id="4ae76-134">选择**域**，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4ae76-134">Select **Domain**, and select **Next**.</span></span>
    5. <span data-ttu-id="4ae76-135">输入任何名称，如`MSDTC for Oracle EBS`，然后选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="4ae76-135">Enter any name, such as `MSDTC for Oracle EBS`, and select **Finish**.</span></span>
  
5.  <span data-ttu-id="4ae76-136">完成向导，并关闭 Windows 防火墙。</span><span class="sxs-lookup"><span data-stu-id="4ae76-136">Complete the wizard, and close Windows Firewall.</span></span> 
  
## <a name="next"></a><span data-ttu-id="4ae76-137">Next</span><span class="sxs-lookup"><span data-stu-id="4ae76-137">Next</span></span> 
[<span data-ttu-id="4ae76-138">Oracle EBS 适配器的的示例</span><span class="sxs-lookup"><span data-stu-id="4ae76-138">Samples for the Oracle EBS adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)