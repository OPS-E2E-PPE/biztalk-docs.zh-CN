---
title: 如何针对 ENTSSO MA 配置 MIIS |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7820384-ff64-4628-9e35-02b13803928f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e536e44ec6c76ba3bf44b346fd6b44e54c3f05b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341298"
---
# <a name="how-to-configure-miis-for-entsso-ma"></a><span data-ttu-id="1c918-102">如何针对 ENTSSO MA 配置 MIIS</span><span class="sxs-lookup"><span data-stu-id="1c918-102">How to Configure MIIS for ENTSSO MA</span></span>
<span data-ttu-id="1c918-103">在运行 Microsoft Identity Integration Server (MIIS) 的计算机上安装企业单一登录 (SSO) 管理功能 （完整版本或仅限管理员的版本），会自动安装 ENTSSO 管理代理。</span><span class="sxs-lookup"><span data-stu-id="1c918-103">When you install the Enterprise Single Sign-On (SSO) Administration feature (either the full version or the Admin-only version) on a computer running Microsoft Identity Integration Server (MIIS), the ENTSSO Management Agent is automatically installed.</span></span> <span data-ttu-id="1c918-104">这意味着，当打开 MIIS 时，几乎所有配置已经完成了。</span><span class="sxs-lookup"><span data-stu-id="1c918-104">This means that when you open MIIS, nearly all of the configuration has already been done.</span></span> <span data-ttu-id="1c918-105">仅缺少的部分是连接信息。</span><span class="sxs-lookup"><span data-stu-id="1c918-105">The only part missing is the connection information.</span></span>  
  
 <span data-ttu-id="1c918-106">在开始之前此过程，请确保具有提供的以下信息：</span><span class="sxs-lookup"><span data-stu-id="1c918-106">Before starting this procedure, make sure you have the following information available:</span></span>  
  
-   <span data-ttu-id="1c918-107">ENTSSO 服务器名称。</span><span class="sxs-lookup"><span data-stu-id="1c918-107">ENTSSO Server name.</span></span>  
  
-   <span data-ttu-id="1c918-108">用户 Id 和在其下 ENTSSO 管理代理将与 SSO 服务器通信的 Windows 帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="1c918-108">UserId and password of the Windows account under which the ENTSSO Management Agent will communicate with the SSO Server.</span></span>  
  
### <a name="to-configure-the-management-agent-within-miis"></a><span data-ttu-id="1c918-109">若要配置 MIIS 中管理代理</span><span class="sxs-lookup"><span data-stu-id="1c918-109">To configure the Management Agent within MIIS</span></span>  
  
1.  <span data-ttu-id="1c918-110">打开 MIIS，并打开**Identity Manager**。</span><span class="sxs-lookup"><span data-stu-id="1c918-110">Open MIIS, and open the **Identity Manager**.</span></span>  
  
2.  <span data-ttu-id="1c918-111">打开**创建管理代理**对话框。</span><span class="sxs-lookup"><span data-stu-id="1c918-111">Open the **Create Management Agent** dialog box.</span></span>  
  
3.  <span data-ttu-id="1c918-112">选择**企业单一登录**列表中。</span><span class="sxs-lookup"><span data-stu-id="1c918-112">Select **Enterprise Single Sign-On** in the list.</span></span>  
  
     <span data-ttu-id="1c918-113">这将启动**创建管理代理向导**。</span><span class="sxs-lookup"><span data-stu-id="1c918-113">This starts the **Create Management Agent Wizard**.</span></span>  
  
4.  <span data-ttu-id="1c918-114">上**配置连接信息**页上，在**连接到：** 字段中，输入 SSO 服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="1c918-114">On the **Configure Connection Information** page, in the **Connect To:** field, enter the name of the SSO Server.</span></span>  
  
5.  <span data-ttu-id="1c918-115">输入 ENTSSO 管理代理的名称。</span><span class="sxs-lookup"><span data-stu-id="1c918-115">Enter the name of the ENTSSO Management Agent.</span></span> <span data-ttu-id="1c918-116">此名称必须与 ENTSSO.xml 文件中指定的名称匹配。</span><span class="sxs-lookup"><span data-stu-id="1c918-116">This name must match the name specified in your ENTSSO.xml file.</span></span>  
  
6.  <span data-ttu-id="1c918-117">在中**用户**字段中，指定 ENTSSO 管理代理使用来管理 SSO 数据库中的映射的域帐户。</span><span class="sxs-lookup"><span data-stu-id="1c918-117">In the **User** field, specify the domain account that the ENTSSO Management Agent uses to manage mappings in the SSO Database.</span></span>  
  
     <span data-ttu-id="1c918-118">此帐户应是 SSO 系统中的 SSO Affiliate Administrators 或 SSO 管理员帐户的成员。</span><span class="sxs-lookup"><span data-stu-id="1c918-118">This account should be either a member of the SSO Affiliate Administrators or SSO Administrators accounts within the SSO System.</span></span>  
  
7.  <span data-ttu-id="1c918-119">在中**密码**字段中，输入该用户的密码。</span><span class="sxs-lookup"><span data-stu-id="1c918-119">In the **Password** field, enter the password for that user.</span></span>  
  
8.  <span data-ttu-id="1c918-120">单击**下一步**，接受默认设置，直到达到**配置扩展**页。</span><span class="sxs-lookup"><span data-stu-id="1c918-120">Click **Next**, accepting the defaults until you reach the **Configure Extensions** page.</span></span>  
  
9. <span data-ttu-id="1c918-121">附近**连接信息**密码扩展，请单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="1c918-121">Near **Connection information** for password extension, click **Settings**.</span></span>  
  
     <span data-ttu-id="1c918-122">**连接设置**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="1c918-122">The **Connection Settings** dialog box appears.</span></span>  
  
10. <span data-ttu-id="1c918-123">在中**连接到**框中，输入相应的帐户。</span><span class="sxs-lookup"><span data-stu-id="1c918-123">In the **Connect To** box, enter the appropriate account.</span></span> <span data-ttu-id="1c918-124">此帐户必须是指定的计算机上运行的 ENTSSO 服务的服务帐户相同。</span><span class="sxs-lookup"><span data-stu-id="1c918-124">This account must be the same as the service account for the ENTSSO service running on the computer specified.</span></span>  
  
11. <span data-ttu-id="1c918-125">在中**用户**并**密码**字段中，输入用户名和密码的帐户。</span><span class="sxs-lookup"><span data-stu-id="1c918-125">In the **User** and **Password** fields, enter the user name and password for the account.</span></span>  
  
12. <span data-ttu-id="1c918-126">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="1c918-126">Click **OK**.</span></span>  
  
13. <span data-ttu-id="1c918-127">在中**MIISCreate 管理代理**，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="1c918-127">In the **MIISCreate Management Agent**, click **Finish**.</span></span>  
  
14. <span data-ttu-id="1c918-128">在仍处于**标识管理器**，单击**工具**菜单，并单击**选项**。</span><span class="sxs-lookup"><span data-stu-id="1c918-128">While still in the **Identity Manager**, click the **Tools** menu, and then click **Options**.</span></span>  
  
     <span data-ttu-id="1c918-129">**选项**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="1c918-129">The **Options** dialog box appears.</span></span>  
  
15. <span data-ttu-id="1c918-130">选择**启用 metaverse 规则扩展**。</span><span class="sxs-lookup"><span data-stu-id="1c918-130">Select **Enable metaverse rules extension**.</span></span>  
  
16. <span data-ttu-id="1c918-131">在中**规则扩展名称字段**，输入**Microsoft.EnterpriseSingleSignOn.ManagementAgent.dll**。</span><span class="sxs-lookup"><span data-stu-id="1c918-131">In the **Rules extension name field**, enter **Microsoft.EnterpriseSingleSignOn.ManagementAgent.dll**.</span></span>  
  
17. <span data-ttu-id="1c918-132">单击**确定**并关闭 MIIS。</span><span class="sxs-lookup"><span data-stu-id="1c918-132">Click **OK** and close MIIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c918-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c918-133">See Also</span></span>  
 [<span data-ttu-id="1c918-134">如何使用 ENTSSO 管理代理</span><span class="sxs-lookup"><span data-stu-id="1c918-134">How to Use the ENTSSO Management Agent</span></span>](../core/how-to-use-the-entsso-management-agent.md)