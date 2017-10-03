---
title: "如何显示和隐藏属性架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [schemas], showing
- schemas, properties
- managing [schemas], hiding
- managing [schemas], properties
ms.assetid: e7cc1838-cc3f-4dd3-a7d1-e66e7ee82d0c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63c2d027255cb4e2ed75b58d4fa11959d67afa2d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-show-and-hide-property-schemas"></a><span data-ttu-id="55c48-102">如何显示和隐藏属性架构</span><span class="sxs-lookup"><span data-stu-id="55c48-102">How to Show and Hide Property Schemas</span></span>
<span data-ttu-id="55c48-103">本主题介绍如何使用 BizTalk Server 管理控制台在应用程序 Schemas 文件夹中显示和隐藏属性架构。</span><span class="sxs-lookup"><span data-stu-id="55c48-103">This topic describes how to use the BizTalk Server Administration console to show and hide property schemas in the Schemas folder for an application.</span></span> <span data-ttu-id="55c48-104">属性架构是 BizTalk 架构的简化版本，它在实例消息和消息上下文之间来回复制升级属性的过程中起到一定作用。</span><span class="sxs-lookup"><span data-stu-id="55c48-104">A property schema is a simple version of a BizTalk schema that plays a role in the process of copying promoted properties back and forth between the instance message and the message context.</span></span> <span data-ttu-id="55c48-105">可能要隐藏属性架构以简化架构视图，从而只显示文档架构。</span><span class="sxs-lookup"><span data-stu-id="55c48-105">You might want to hide property schemas to simplify the schema view, so that you only see document schemas.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="55c48-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="55c48-106">Prerequisites</span></span>  
 <span data-ttu-id="55c48-107">若要执行本主题中描述的过程，必须以 BizTalk Server Administrators 组或 BizTalk Server Operators 组成员的帐户身份登录。</span><span class="sxs-lookup"><span data-stu-id="55c48-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group or BizTalk Server Operators group.</span></span> <span data-ttu-id="55c48-108">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="55c48-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-show-or-hide-property-schemas-in-the-schemas-folder"></a><span data-ttu-id="55c48-109">在 Schemas 文件夹中显示或隐藏属性架构</span><span class="sxs-lookup"><span data-stu-id="55c48-109">To show or hide property schemas in the Schemas folder</span></span>  
  
1.  <span data-ttu-id="55c48-110">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="55c48-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="55c48-111">在控制台树中，展开**BizTalk Server 管理**，展开包含想要显示或隐藏属性架构的架构文件夹的 BizTalk 组，然后展开包含架构文件夹的应用程序。</span><span class="sxs-lookup"><span data-stu-id="55c48-111">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the schemas folder in which you want to show or hide property schemas, and then expand the application containing the schemas folder.</span></span>  
  
3.  <span data-ttu-id="55c48-112">右键单击**架构**文件夹，然后单击**隐藏属性架构**或**显示属性架构**。</span><span class="sxs-lookup"><span data-stu-id="55c48-112">Right-click the **Schemas** folder, and click either **Hide Property Schemas** or **Show Property Schemas**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c48-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55c48-113">See Also</span></span>  
 [<span data-ttu-id="55c48-114">管理架构</span><span class="sxs-lookup"><span data-stu-id="55c48-114">Managing Schemas</span></span>](../core/managing-schemas.md)