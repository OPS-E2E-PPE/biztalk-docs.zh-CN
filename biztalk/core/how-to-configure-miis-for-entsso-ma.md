---
title: "如何为 ENTSSO MA 配置 MIIS |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7820384-ff64-4628-9e35-02b13803928f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 969a52beb02c3d2ba237369c16efec9ee84e2ef1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-miis-for-entsso-ma"></a><span data-ttu-id="50557-102">如何针对 ENTSSO MA 配置 MIIS</span><span class="sxs-lookup"><span data-stu-id="50557-102">How to Configure MIIS for ENTSSO MA</span></span>
<span data-ttu-id="50557-103">当在运行 Microsoft Identity Integration Server (MIIS) 的计算机上安装企业单一登录 (SSO) 管理功能（完整版本或仅管理版本）时，将自动安装 ENTSSO 管理代理。</span><span class="sxs-lookup"><span data-stu-id="50557-103">When you install the Enterprise Single Sign-On (SSO) Administration feature (either the full version or the Admin-only version) on a computer running Microsoft Identity Integration Server (MIIS), the ENTSSO Management Agent is automatically installed.</span></span> <span data-ttu-id="50557-104">这表示当打开 MIIS 时，几乎已完成所有配置，</span><span class="sxs-lookup"><span data-stu-id="50557-104">This means that when you open MIIS, nearly all of the configuration has already been done.</span></span> <span data-ttu-id="50557-105">唯一缺少的部分是连接信息。</span><span class="sxs-lookup"><span data-stu-id="50557-105">The only part missing is the connection information.</span></span>  
  
 <span data-ttu-id="50557-106">在启动此过程前，请确保具有下列可用信息：</span><span class="sxs-lookup"><span data-stu-id="50557-106">Before starting this procedure, make sure you have the following information available:</span></span>  
  
-   <span data-ttu-id="50557-107">ENTSSO 服务器名称。</span><span class="sxs-lookup"><span data-stu-id="50557-107">ENTSSO Server name.</span></span>  
  
-   <span data-ttu-id="50557-108">ENTSSO 管理代理与 SSO 服务器通信所使用的 Windows 帐户的用户 ID 和密码。</span><span class="sxs-lookup"><span data-stu-id="50557-108">UserId and password of the Windows account under which the ENTSSO Management Agent will communicate with the SSO Server.</span></span>  
  
### <a name="to-configure-the-management-agent-within-miis"></a><span data-ttu-id="50557-109">在 MIIS 中配置管理代理</span><span class="sxs-lookup"><span data-stu-id="50557-109">To configure the Management Agent within MIIS</span></span>  
  
1.  <span data-ttu-id="50557-110">打开 miis 进行，并打开**Identity Manager**。</span><span class="sxs-lookup"><span data-stu-id="50557-110">Open MIIS, and open the **Identity Manager**.</span></span>  
  
2.  <span data-ttu-id="50557-111">打开**创建管理代理**对话框。</span><span class="sxs-lookup"><span data-stu-id="50557-111">Open the **Create Management Agent** dialog box.</span></span>  
  
3.  <span data-ttu-id="50557-112">选择**企业单一登录**列表中。</span><span class="sxs-lookup"><span data-stu-id="50557-112">Select **Enterprise Single Sign-On** in the list.</span></span>  
  
     <span data-ttu-id="50557-113">这将启动**创建管理代理向导**。</span><span class="sxs-lookup"><span data-stu-id="50557-113">This starts the **Create Management Agent Wizard**.</span></span>  
  
4.  <span data-ttu-id="50557-114">上**配置连接信息**页上，在**连接到：**字段中，输入 SSO 服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="50557-114">On the **Configure Connection Information** page, in the **Connect To:** field, enter the name of the SSO Server.</span></span>  
  
5.  <span data-ttu-id="50557-115">输入 ENTSSO 管理代理的名称。</span><span class="sxs-lookup"><span data-stu-id="50557-115">Enter the name of the ENTSSO Management Agent.</span></span> <span data-ttu-id="50557-116">该名称必须与 ENTSSO.xml 文件中指定的名称匹配。</span><span class="sxs-lookup"><span data-stu-id="50557-116">This name must match the name specified in your ENTSSO.xml file.</span></span>  
  
6.  <span data-ttu-id="50557-117">在**用户**字段中，指定用于管理 SSO 数据库中的映射 ENTSSO 管理代理的域帐户。</span><span class="sxs-lookup"><span data-stu-id="50557-117">In the **User** field, specify the domain account that the ENTSSO Management Agent uses to manage mappings in the SSO Database.</span></span>  
  
     <span data-ttu-id="50557-118">此帐户应是 SSO 系统中的 SSO Affiliate Administrators 或 SSO Administrator 帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="50557-118">This account should be either a member of the SSO Affiliate Administrators or SSO Administrators accounts within the SSO System.</span></span>  
  
7.  <span data-ttu-id="50557-119">在**密码**字段中，输入该用户的密码。</span><span class="sxs-lookup"><span data-stu-id="50557-119">In the **Password** field, enter the password for that user.</span></span>  
  
8.  <span data-ttu-id="50557-120">单击**下一步**，接受默认值，直至到达**配置扩展**页。</span><span class="sxs-lookup"><span data-stu-id="50557-120">Click **Next**, accepting the defaults until you reach the **Configure Extensions** page.</span></span>  
  
9. <span data-ttu-id="50557-121">附近**连接信息**密码扩展，请单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="50557-121">Near **Connection information** for password extension, click **Settings**.</span></span>  
  
     <span data-ttu-id="50557-122">**连接设置**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="50557-122">The **Connection Settings** dialog box appears.</span></span>  
  
10. <span data-ttu-id="50557-123">在**连接到**框中，输入合适的帐户。</span><span class="sxs-lookup"><span data-stu-id="50557-123">In the **Connect To** box, enter the appropriate account.</span></span> <span data-ttu-id="50557-124">该帐户必须与指定计算机上运行的 ENTSSO 服务的服务帐户相同。</span><span class="sxs-lookup"><span data-stu-id="50557-124">This account must be the same as the service account for the ENTSSO service running on the computer specified.</span></span>  
  
11. <span data-ttu-id="50557-125">在**用户**和**密码**字段，输入帐户的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="50557-125">In the **User** and **Password** fields, enter the user name and password for the account.</span></span>  
  
12. <span data-ttu-id="50557-126">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="50557-126">Click **OK**.</span></span>  
  
13. <span data-ttu-id="50557-127">在**MIISCreate 管理代理**，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="50557-127">In the **MIISCreate Management Agent**, click **Finish**.</span></span>  
  
14. <span data-ttu-id="50557-128">仍中时，在**Identity Manager**，单击**工具**菜单，，然后单击**选项**。</span><span class="sxs-lookup"><span data-stu-id="50557-128">While still in the **Identity Manager**, click the **Tools** menu, and then click **Options**.</span></span>  
  
     <span data-ttu-id="50557-129">**选项**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="50557-129">The **Options** dialog box appears.</span></span>  
  
15. <span data-ttu-id="50557-130">选择**启用 metaverse 规则扩展**。</span><span class="sxs-lookup"><span data-stu-id="50557-130">Select **Enable metaverse rules extension**.</span></span>  
  
16. <span data-ttu-id="50557-131">在**规则扩展名称字段**，输入**Microsoft.EnterpriseSingleSignOn.ManagementAgent.dll**。</span><span class="sxs-lookup"><span data-stu-id="50557-131">In the **Rules extension name field**, enter **Microsoft.EnterpriseSingleSignOn.ManagementAgent.dll**.</span></span>  
  
17. <span data-ttu-id="50557-132">单击**确定**并关闭 miis 进行。</span><span class="sxs-lookup"><span data-stu-id="50557-132">Click **OK** and close MIIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50557-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50557-133">See Also</span></span>  
 [<span data-ttu-id="50557-134">如何使用 ENTSSO 管理代理</span><span class="sxs-lookup"><span data-stu-id="50557-134">How to Use the ENTSSO Management Agent</span></span>](../core/how-to-use-the-entsso-management-agent.md)