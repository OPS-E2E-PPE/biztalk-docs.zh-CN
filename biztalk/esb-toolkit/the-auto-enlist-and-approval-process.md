---
title: 自动登记和审批流程 |Microsoft Docs
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
ms.openlocfilehash: aafe1e5557d61303370b2119a82340288d8744f1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399872"
---
# <a name="the-auto-enlist-and-approval-process"></a><span data-ttu-id="29cfc-102">自动登记和审批过程</span><span class="sxs-lookup"><span data-stu-id="29cfc-102">The Auto-Enlist and Approval Process</span></span>
<span data-ttu-id="29cfc-103">可以配置 ESB 管理门户以两种方式发布 Microsoft BizTalk Server 终结点：</span><span class="sxs-lookup"><span data-stu-id="29cfc-103">You can configure the ESB Management Portal to publish Microsoft BizTalk Server endpoints in two ways:</span></span>  
  
- <span data-ttu-id="29cfc-104">它可以通过审批过程，管理员必须确认和审批注册请求的配置。</span><span class="sxs-lookup"><span data-stu-id="29cfc-104">It can be configured through the approval process, where an administrator must confirm and approve the registration request.</span></span>  
  
- <span data-ttu-id="29cfc-105">这可以通过使用配置自动发布，其中在门户仪表板请求到通用描述、 发现和集成 (UDDI) 注册表而无需管理员干预。</span><span class="sxs-lookup"><span data-stu-id="29cfc-105">It can be configured by using auto-publish, where the portal automatically publishes the request into the Universal Description, Discovery, and Integration (UDDI) registry without requiring administrator intervention.</span></span>  
  
  <span data-ttu-id="29cfc-106">以下两个过程中所述，还可以指定多个其他设置的门户中，UDDI 集成功能。</span><span class="sxs-lookup"><span data-stu-id="29cfc-106">You can also specify several other settings of the UDDI Integration features of the portal, as described in the following two procedures.</span></span>  
  
### <a name="to-configure-auto-approval-and-publishing-in-the-esb-management-portal"></a><span data-ttu-id="29cfc-107">ESB 管理门户中配置自动审批和发布</span><span class="sxs-lookup"><span data-stu-id="29cfc-107">To configure auto-approval and publishing in the ESB Management Portal</span></span>  
  
1.  <span data-ttu-id="29cfc-108">请确保您登录到在门户中使用该帐户是 BizTalk Server Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="29cfc-108">Make sure that you log on to the portal using an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
2.  <span data-ttu-id="29cfc-109">指向**管理员**在门户的主菜单上，选项卡，然后单击**注册表设置**以打开门户[注册表设置页](../esb-toolkit/registry-settings-page.md)。</span><span class="sxs-lookup"><span data-stu-id="29cfc-109">Point to the **Admin** tab on the portal main menu, and then click **Registry Settings** to open the portal [Registry Settings Page](../esb-toolkit/registry-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="29cfc-110">若要启用自动审批和发布，可在顶部文本框中键入 UDDI 服务器的 URL **UDDI 的详细信息**部分中的页上，并选择**以自动发布**复选框。</span><span class="sxs-lookup"><span data-stu-id="29cfc-110">To enable auto-approval and publishing, type the URL of your UDDI server in the text box at the top of the **UDDI Details** section of the page, and then select the **AutoPublish** check box.</span></span>  
  
4.  <span data-ttu-id="29cfc-111">若要禁用自动审批和发布，请清除**自动发布**复选框。</span><span class="sxs-lookup"><span data-stu-id="29cfc-111">To disable auto-approval and publishing, clear the **Auto Publish** check box.</span></span>  
  
### <a name="to-configure-e-mail-and-registry-settings-for-the-uddi-integration-features"></a><span data-ttu-id="29cfc-112">若要配置的 UDDI 集成功能的电子邮件和注册表设置</span><span class="sxs-lookup"><span data-stu-id="29cfc-112">To configure e-mail and registry settings for the UDDI Integration features</span></span>  
  
1.  <span data-ttu-id="29cfc-113">请确保您登录到在门户中使用该帐户是 BizTalk Server 管理员帐户组的成员。</span><span class="sxs-lookup"><span data-stu-id="29cfc-113">Make sure that you log on to the portal using an account that is a member of the BizTalk Server Administrators account group.</span></span>  
  
2.  <span data-ttu-id="29cfc-114">指向**管理员**在门户的主菜单上，选项卡，然后单击**注册表设置**以打开门户[注册表设置页](../esb-toolkit/registry-settings-page.md)。</span><span class="sxs-lookup"><span data-stu-id="29cfc-114">Point to the **Admin** tab on the portal main menu, and then click **Registry Settings** to open the portal [Registry Settings Page](../esb-toolkit/registry-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="29cfc-115">编辑 UDDI 服务器顶部的文本框中的 URL **UDDI 的详细信息**页部分。</span><span class="sxs-lookup"><span data-stu-id="29cfc-115">Edit the URL of your UDDI server in the text box at the top of the **UDDI Details** section of the page.</span></span> <span data-ttu-id="29cfc-116">默认的 UDDI 服务是本地的 Microsoft UDDI 服务。</span><span class="sxs-lookup"><span data-stu-id="29cfc-116">The default UDDI service is the local Microsoft UDDI service.</span></span>  
  
4.  <span data-ttu-id="29cfc-117">选择**Anonymous**复选框，如果希望在门户中访问 UDDI 服务器时使用匿名身份验证。</span><span class="sxs-lookup"><span data-stu-id="29cfc-117">Select the **Anonymous** check box if you want the portal to use anonymous authentication when accessing the UDDI server.</span></span>  
  
5.  <span data-ttu-id="29cfc-118">如果希望在门户中通过电子邮件时 UDDI 发布通知您的请求正在等待批准，请选择**启用通知**中的复选框**电子邮件通知**页部分。</span><span class="sxs-lookup"><span data-stu-id="29cfc-118">If you want the portal to notify you by e-mail when a UDDI publishing request is awaiting approval, select the **Notification Enabled** check box in the **Email Notification** section of the page.</span></span> <span data-ttu-id="29cfc-119">然后输入电子邮件服务器、 发送电子邮件地址、 相应的 '发件人"电子邮件地址、 邮件主题和消息正文的详细信息。</span><span class="sxs-lookup"><span data-stu-id="29cfc-119">Then enter the details of your e-mail server, the address for delivery of e-mail messages, an appropriate "from" e-mail address, the message subject, and the message body.</span></span>  
  
6.  <span data-ttu-id="29cfc-120">输入管理员联系人姓名和电子邮件地址的 UDDI 回执请求中的电子邮件**默认设置**页部分。</span><span class="sxs-lookup"><span data-stu-id="29cfc-120">Enter the administrator contact name and e-mail address for the receipt of UDDI request e-mail messages in the **Default Settings** section of the page.</span></span>  
  
### <a name="to-approve-or-decline-a-registration-request-as-an-administrator"></a><span data-ttu-id="29cfc-121">若要批准或拒绝以管理员身份注册请求</span><span class="sxs-lookup"><span data-stu-id="29cfc-121">To approve or decline a registration request as an administrator</span></span>  
  
1.  <span data-ttu-id="29cfc-122">请确保登录到在门户中使用该帐户是 BizTalk Server Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="29cfc-122">Make sure that you log into the portal using an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
2.  <span data-ttu-id="29cfc-123">指向**注册表**在门户的主菜单上，选项卡，然后单击**管理挂起的请求**以打开门户[管理挂起的请求页](../esb-toolkit/manage-pending-requests-page.md)。</span><span class="sxs-lookup"><span data-stu-id="29cfc-123">Point to the **Registry** tab on the portal main menu, and then click **Manage Pending Requests** to open the portal [Manage Pending Requests Page](../esb-toolkit/manage-pending-requests-page.md).</span></span>  
  
3.  <span data-ttu-id="29cfc-124">若要批准挂起的请求，请单击**批准**列表中该请求旁边的图标 （复选标记）。</span><span class="sxs-lookup"><span data-stu-id="29cfc-124">To approve a pending request, click the **Approve** icon (the check mark) next to that request in the list.</span></span>  
  
4.  <span data-ttu-id="29cfc-125">若要拒绝挂起的请求，请单击**拒绝**列表中该请求旁边的图标 （十字标记）。</span><span class="sxs-lookup"><span data-stu-id="29cfc-125">To reject a pending request, click the **Reject** icon (the cross mark) next to that request in the list.</span></span>  
  
5.  <span data-ttu-id="29cfc-126">若要查看挂起的请求的详细信息，请单击**查看详细信息**图标 （放大镜） 以打开[注册表详细信息页](../esb-toolkit/registry-details-page.md)。</span><span class="sxs-lookup"><span data-stu-id="29cfc-126">To view details of a pending request, click the **View Details** icon (the magnifying glass) to open the [Registry Details Page](../esb-toolkit/registry-details-page.md).</span></span> <span data-ttu-id="29cfc-127">您可以发布、 删除或更新此页中的请求。</span><span class="sxs-lookup"><span data-stu-id="29cfc-127">You can publish, delete, or update the request in this page.</span></span>  
  
6.  <span data-ttu-id="29cfc-128">若要查看请求状态，并查看以前的请求的列表，请单击**查看请求历史记录**链接。</span><span class="sxs-lookup"><span data-stu-id="29cfc-128">To review the requests status and see a list of previous requests, click the **View Request History** link.</span></span>