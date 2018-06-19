---
title: 自动登记和审批过程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dfd3e72e-e28b-4ee3-bc4a-89ef3f64e6d5
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 333e1403ffd45f80a98d3eb17f5d3aa2b63c7798
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295621"
---
# <a name="the-auto-enlist-and-approval-process"></a><span data-ttu-id="2fe22-102">自动登记和审批过程</span><span class="sxs-lookup"><span data-stu-id="2fe22-102">The Auto-Enlist and Approval Process</span></span>
<span data-ttu-id="2fe22-103">你可以配置 ESB 管理门户以两种方式发布 Microsoft BizTalk Server 终结点：</span><span class="sxs-lookup"><span data-stu-id="2fe22-103">You can configure the ESB Management Portal to publish Microsoft BizTalk Server endpoints in two ways:</span></span>  
  
-   <span data-ttu-id="2fe22-104">它可以通过审批过程，其中管理员必须确认和审批注册请求配置。</span><span class="sxs-lookup"><span data-stu-id="2fe22-104">It can be configured through the approval process, where an administrator must confirm and approve the registration request.</span></span>  
  
-   <span data-ttu-id="2fe22-105">这可以通过使用配置自动发布，其中门户仪表板请求到通用、 描述、 发现和集成 (UDDI) 注册表而无需管理员干预。</span><span class="sxs-lookup"><span data-stu-id="2fe22-105">It can be configured by using auto-publish, where the portal automatically publishes the request into the Universal Description, Discovery, and Integration (UDDI) registry without requiring administrator intervention.</span></span>  
  
 <span data-ttu-id="2fe22-106">以下两个过程中所述，还可以指定多个门户中，UDDI 集成功能的其他设置。</span><span class="sxs-lookup"><span data-stu-id="2fe22-106">You can also specify several other settings of the UDDI Integration features of the portal, as described in the following two procedures.</span></span>  
  
### <a name="to-configure-auto-approval-and-publishing-in-the-esb-management-portal"></a><span data-ttu-id="2fe22-107">若要在 ESB 管理门户中配置自动批准和发布</span><span class="sxs-lookup"><span data-stu-id="2fe22-107">To configure auto-approval and publishing in the ESB Management Portal</span></span>  
  
1.  <span data-ttu-id="2fe22-108">请确保您登录到使用 BizTalk Server Administrators 组的成员的帐户门户。</span><span class="sxs-lookup"><span data-stu-id="2fe22-108">Make sure that you log on to the portal using an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
2.  <span data-ttu-id="2fe22-109">指向**管理员**在门户的主菜单上，选项卡，然后单击**注册表设置**以打开门户[注册表设置页](../esb-toolkit/registry-settings-page.md)。</span><span class="sxs-lookup"><span data-stu-id="2fe22-109">Point to the **Admin** tab on the portal main menu, and then click **Registry Settings** to open the portal [Registry Settings Page](../esb-toolkit/registry-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="2fe22-110">若要启用自动批准和发布，在顶部的文本框中键入 UDDI 服务器的 URL **UDDI 详细信息**部分页上，，然后选择**自动发布**复选框。</span><span class="sxs-lookup"><span data-stu-id="2fe22-110">To enable auto-approval and publishing, type the URL of your UDDI server in the text box at the top of the **UDDI Details** section of the page, and then select the **AutoPublish** check box.</span></span>  
  
4.  <span data-ttu-id="2fe22-111">若要禁用自动批准和发布，清除**自动发布**复选框。</span><span class="sxs-lookup"><span data-stu-id="2fe22-111">To disable auto-approval and publishing, clear the **Auto Publish** check box.</span></span>  
  
### <a name="to-configure-e-mail-and-registry-settings-for-the-uddi-integration-features"></a><span data-ttu-id="2fe22-112">若要配置的 UDDI 集成功能的电子邮件和注册表设置</span><span class="sxs-lookup"><span data-stu-id="2fe22-112">To configure e-mail and registry settings for the UDDI Integration features</span></span>  
  
1.  <span data-ttu-id="2fe22-113">请确保您登录到使用 BizTalk Server Administrators 帐户组的成员的帐户门户。</span><span class="sxs-lookup"><span data-stu-id="2fe22-113">Make sure that you log on to the portal using an account that is a member of the BizTalk Server Administrators account group.</span></span>  
  
2.  <span data-ttu-id="2fe22-114">指向**管理员**在门户的主菜单上，选项卡，然后单击**注册表设置**以打开门户[注册表设置页](../esb-toolkit/registry-settings-page.md)。</span><span class="sxs-lookup"><span data-stu-id="2fe22-114">Point to the **Admin** tab on the portal main menu, and then click **Registry Settings** to open the portal [Registry Settings Page](../esb-toolkit/registry-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="2fe22-115">编辑 UDDI 服务器在顶部的文本框中的 URL **UDDI 详细信息**页的部分。</span><span class="sxs-lookup"><span data-stu-id="2fe22-115">Edit the URL of your UDDI server in the text box at the top of the **UDDI Details** section of the page.</span></span> <span data-ttu-id="2fe22-116">默认 UDDI 服务是本地的 Microsoft UDDI 服务。</span><span class="sxs-lookup"><span data-stu-id="2fe22-116">The default UDDI service is the local Microsoft UDDI service.</span></span>  
  
4.  <span data-ttu-id="2fe22-117">选择**匿名**复选框，如果你希望在门户中访问 UDDI 服务器时使用匿名身份验证。</span><span class="sxs-lookup"><span data-stu-id="2fe22-117">Select the **Anonymous** check box if you want the portal to use anonymous authentication when accessing the UDDI server.</span></span>  
  
5.  <span data-ttu-id="2fe22-118">如果你希望在门户以通过电子邮件时 UDDI 发布通知你的请求正在等待批准，请选择**启用通知**中的复选框**电子邮件通知**页的部分。</span><span class="sxs-lookup"><span data-stu-id="2fe22-118">If you want the portal to notify you by e-mail when a UDDI publishing request is awaiting approval, select the **Notification Enabled** check box in the **Email Notification** section of the page.</span></span> <span data-ttu-id="2fe22-119">然后输入电子邮件服务器、 电子邮件的传递地址、 适当 '发件人"电子邮件地址、 邮件主题和消息正文的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2fe22-119">Then enter the details of your e-mail server, the address for delivery of e-mail messages, an appropriate "from" e-mail address, the message subject, and the message body.</span></span>  
  
6.  <span data-ttu-id="2fe22-120">输入管理员联系人姓名和电子邮件地址为 UDDI 接收请求中的电子邮件**默认设置**页的部分。</span><span class="sxs-lookup"><span data-stu-id="2fe22-120">Enter the administrator contact name and e-mail address for the receipt of UDDI request e-mail messages in the **Default Settings** section of the page.</span></span>  
  
### <a name="to-approve-or-decline-a-registration-request-as-an-administrator"></a><span data-ttu-id="2fe22-121">若要批准或拒绝以管理员身份注册请求</span><span class="sxs-lookup"><span data-stu-id="2fe22-121">To approve or decline a registration request as an administrator</span></span>  
  
1.  <span data-ttu-id="2fe22-122">请确保你登录到使用 BizTalk Server Administrators 组的成员的帐户门户。</span><span class="sxs-lookup"><span data-stu-id="2fe22-122">Make sure that you log into the portal using an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
2.  <span data-ttu-id="2fe22-123">指向**注册表**在门户的主菜单上，选项卡，然后单击**管理挂起的请求**以打开门户[管理挂起的请求页](../esb-toolkit/manage-pending-requests-page.md)。</span><span class="sxs-lookup"><span data-stu-id="2fe22-123">Point to the **Registry** tab on the portal main menu, and then click **Manage Pending Requests** to open the portal [Manage Pending Requests Page](../esb-toolkit/manage-pending-requests-page.md).</span></span>  
  
3.  <span data-ttu-id="2fe22-124">若要批准挂起的请求，请单击**批准**列表中该请求旁边的图标 （复选标记）。</span><span class="sxs-lookup"><span data-stu-id="2fe22-124">To approve a pending request, click the **Approve** icon (the check mark) next to that request in the list.</span></span>  
  
4.  <span data-ttu-id="2fe22-125">若要拒绝挂起的请求，请单击**拒绝**列表中该请求旁边的图标 （交叉标记）。</span><span class="sxs-lookup"><span data-stu-id="2fe22-125">To reject a pending request, click the **Reject** icon (the cross mark) next to that request in the list.</span></span>  
  
5.  <span data-ttu-id="2fe22-126">若要查看的挂起请求的详细信息，请单击**查看详细信息**图标 （放大镜） 以打开[注册表的详细信息页](../esb-toolkit/registry-details-page.md)。</span><span class="sxs-lookup"><span data-stu-id="2fe22-126">To view details of a pending request, click the **View Details** icon (the magnifying glass) to open the [Registry Details Page](../esb-toolkit/registry-details-page.md).</span></span> <span data-ttu-id="2fe22-127">你可以发布、 删除或更新此页中的请求。</span><span class="sxs-lookup"><span data-stu-id="2fe22-127">You can publish, delete, or update the request in this page.</span></span>  
  
6.  <span data-ttu-id="2fe22-128">若要查看请求状态，并查看以前的请求的列表，请单击**查看请求历史记录**链接。</span><span class="sxs-lookup"><span data-stu-id="2fe22-128">To review the requests status and see a list of previous requests, click the **View Request History** link.</span></span>