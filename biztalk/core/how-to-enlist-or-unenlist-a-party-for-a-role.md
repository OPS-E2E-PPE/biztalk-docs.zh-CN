---
title: 如何登记或取消登记角色参与方 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [role links], enlisting
- enlisting, role links
- role links, unenlisting
- role links, enlisting
- managing [role links], unenlisting
ms.assetid: 06fc2a64-3add-400c-9f9d-fab22fdf5366
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 095a1c2a180c0592641cd791875f23d633d908c8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337837"
---
# <a name="how-to-enlist-or-unenlist-a-party-for-a-role"></a><span data-ttu-id="c7fee-102">如何登记或取消登记角色参与方</span><span class="sxs-lookup"><span data-stu-id="c7fee-102">How to Enlist or Unenlist a Party for a Role</span></span>
<span data-ttu-id="c7fee-103">本主题介绍如何使用 BizTalk Server 管理控制台来登记或取消登记角色参与方。</span><span class="sxs-lookup"><span data-stu-id="c7fee-103">This topic describes how to use the BizTalk Server Administration console to enlist or unenlist a party for a role.</span></span> <span data-ttu-id="c7fee-104">登记参与方的角色分配给该角色的参与方和取消登记参与方从角色中删除该参与方。</span><span class="sxs-lookup"><span data-stu-id="c7fee-104">Enlisting a party for a role assigns the party to the role and unenlisting the party removes the party from the role.</span></span>  
  
 <span data-ttu-id="c7fee-105">当登记或取消登记角色参与方时，请记住以下几点：</span><span class="sxs-lookup"><span data-stu-id="c7fee-105">When enlisting or unenlisting a party for a role, bear in mind the following points:</span></span>  
  
-   <span data-ttu-id="c7fee-106">您可以登记之前，必须创建参与方。</span><span class="sxs-lookup"><span data-stu-id="c7fee-106">You must create a party before you can enlist it.</span></span> <span data-ttu-id="c7fee-107">有关说明，请参阅[如何创建参与方](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044)。</span><span class="sxs-lookup"><span data-stu-id="c7fee-107">For instructions, see [How to Create a Party](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044).</span></span>  
  
-   <span data-ttu-id="c7fee-108">您可以登记或取消角色参与方登记而无需重新启动该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c7fee-108">You can enlist or unenlist a party for a role without needing to restart the application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7fee-109">应用程序开发人员可以登记或取消参与方登记在开发过程中，通过使用本主题中的过程。</span><span class="sxs-lookup"><span data-stu-id="c7fee-109">The application developer can enlist or unenlist a party during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c7fee-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="c7fee-110">Prerequisites</span></span>  
 <span data-ttu-id="c7fee-111">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="c7fee-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="c7fee-112">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="c7fee-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-enlist-or-unenlist-a-party-for-a-role"></a><span data-ttu-id="c7fee-113">若要登记或取消登记角色参与方</span><span class="sxs-lookup"><span data-stu-id="c7fee-113">To enlist or unenlist a party for a role</span></span>  
  
1. <span data-ttu-id="c7fee-114">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="c7fee-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="c7fee-115">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含要登记的角色链接的应用程序或取消登记参与方。</span><span class="sxs-lookup"><span data-stu-id="c7fee-115">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the role link for which you want to enlist or unenlist a party.</span></span>  
  
3. <span data-ttu-id="c7fee-116">单击**角色链接**，右键单击你想要登记或取消登记参与方，然后单击该角色链接**属性**。</span><span class="sxs-lookup"><span data-stu-id="c7fee-116">Click **Role Links**, right-click the role link for which you want to enlist or unenlist a party, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="c7fee-117">登记参与方，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c7fee-117">To enlist a party, do the following:</span></span>  
  
   -   <span data-ttu-id="c7fee-118">单击**登记**单击要登记的参与方。</span><span class="sxs-lookup"><span data-stu-id="c7fee-118">Click **Enlist** and click the party to enlist.</span></span>  
  
   -   <span data-ttu-id="c7fee-119">单击**绑定**，在**发送端口**下拉列表中，单击发送端口要用于此参与方，然后单击**确定**两次。</span><span class="sxs-lookup"><span data-stu-id="c7fee-119">Click **Bind**, in the **Send Port** drop-down list, click the send port to use for this party, and then click **OK** twice.</span></span>  
  
5. <span data-ttu-id="c7fee-120">若要取消登记参与方，单击的参与方，单击**取消登记**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c7fee-120">To unenlist a party, click the party, click **Unenlist**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7fee-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="c7fee-121">See Also</span></span>  
 [<span data-ttu-id="c7fee-122">管理角色链接</span><span class="sxs-lookup"><span data-stu-id="c7fee-122">Managing Role Links</span></span>](../core/managing-role-links.md)