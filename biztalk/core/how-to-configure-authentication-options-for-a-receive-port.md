---
title: 如何配置身份验证选项为接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- authenticating, configuring
- managing [receive ports], authenticating
- receive ports, configuring
- configuring, authenticating
- configuring, receive ports
- authenticating, receive ports
ms.assetid: ce213ef0-ae91-47cf-84bf-0f86cc684bce
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52ca3f5d4636f0592c98528d481a8d3f0a1bc96b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001774"
---
# <a name="how-to-configure-authentication-options-for-a-receive-port"></a><span data-ttu-id="54e8e-102">如何为接收端口配置验证选项</span><span class="sxs-lookup"><span data-stu-id="54e8e-102">How to Configure Authentication Options for a Receive Port</span></span>
<span data-ttu-id="54e8e-103">本主题将介绍如何使用 BizTalk Server 管理控制台为接收端口配置消息验证选项。</span><span class="sxs-lookup"><span data-stu-id="54e8e-103">This topic describes how to use the BizTalk Server Administration console to configure message authentication options for a receive port.</span></span> <span data-ttu-id="54e8e-104">此选项在配置了参与方解析验证后生效。</span><span class="sxs-lookup"><span data-stu-id="54e8e-104">These options take effect when party resolution authentication is configured.</span></span> <span data-ttu-id="54e8e-105">相应的选项包括：</span><span class="sxs-lookup"><span data-stu-id="54e8e-105">The options are:</span></span>  
  
- <span data-ttu-id="54e8e-106">**无身份验证。**</span><span class="sxs-lookup"><span data-stu-id="54e8e-106">**No authentication.**</span></span> <span data-ttu-id="54e8e-107">如果选中此选项，接收端口将以直通方式传送消息而不检查消息凭据。</span><span class="sxs-lookup"><span data-stu-id="54e8e-107">If this option is selected, the receive port will pass the message through without checking for message credentials.</span></span>  
  
- <span data-ttu-id="54e8e-108">**身份验证失败时删除消息。**</span><span class="sxs-lookup"><span data-stu-id="54e8e-108">**Drop messages if authentication fails.**</span></span> <span data-ttu-id="54e8e-109">如果选中此选项，则接收端口将使用参与方解析检查消息凭据，并在验证失败时放弃消息。</span><span class="sxs-lookup"><span data-stu-id="54e8e-109">If this option is selected, the receive port will check message credentials using Party resolution and discard the message if authentication fails.</span></span>  
  
- <span data-ttu-id="54e8e-110">**身份验证失败时保留消息。**</span><span class="sxs-lookup"><span data-stu-id="54e8e-110">**Keep messages if authentication fails.**</span></span> <span data-ttu-id="54e8e-111">如果选中此选项，则接收端口将使用参与方解析检查消息凭据，并在验证失败时在挂起的队列中保留消息。</span><span class="sxs-lookup"><span data-stu-id="54e8e-111">If this option is selected, the receive port will check message credentials using Party resolution and keep the message in the suspended queue if authentication fails.</span></span>  
  
  <span data-ttu-id="54e8e-112">有关创建和配置的参与方的说明，请参阅[如何创建参与方](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044)。</span><span class="sxs-lookup"><span data-stu-id="54e8e-112">For instructions on creating and configuring a party, see [How to Create a Party](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044).</span></span> <span data-ttu-id="54e8e-113">有关参与方解析验证的详细信息，请参阅[进行身份验证消息的发件人](../core/authenticating-the-sender-of-a-message.md)并[入站消息身份验证](../core/inbound-message-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="54e8e-113">For more information about party resolution authentication, see [Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md) and [Inbound Message Authentication](../core/inbound-message-authentication.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="54e8e-114">必要條件</span><span class="sxs-lookup"><span data-stu-id="54e8e-114">Prerequisites</span></span>  
 <span data-ttu-id="54e8e-115">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="54e8e-115">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="54e8e-116">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="54e8e-116">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-authentication-options-for-a-receive-port"></a><span data-ttu-id="54e8e-117">为接收端口配置验证选项</span><span class="sxs-lookup"><span data-stu-id="54e8e-117">To configure authentication options for a receive port</span></span>  
  
1. <span data-ttu-id="54e8e-118">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="54e8e-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="54e8e-119">在控制台树中，展开要为其配置验证的接收端口所属的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="54e8e-119">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure authentication for a receive port.</span></span>  
  
3. <span data-ttu-id="54e8e-120">单击**接收端口**，右键单击接收端口，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="54e8e-120">Click **Receive Ports**, right-click the receive port, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="54e8e-121">在中**身份验证**部分中，选择的选项，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="54e8e-121">In the **Authentication** section, select the option you want, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54e8e-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="54e8e-122">See Also</span></span>  
 [<span data-ttu-id="54e8e-123">管理接收端口</span><span class="sxs-lookup"><span data-stu-id="54e8e-123">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)