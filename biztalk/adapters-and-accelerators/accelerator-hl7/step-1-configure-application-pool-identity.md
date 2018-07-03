---
title: 步骤 1： 配置应用程序池标识 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, application pools
- application pools
ms.assetid: 66286327-8580-4378-89ee-ddd7204b03c6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61cdbc019b2e36ea8c50d97ff03597374cb07253
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988486"
---
# <a name="step-1-configure-application-pool-identity"></a><span data-ttu-id="db5d7-102">步骤 1： 配置应用程序池标识</span><span class="sxs-lookup"><span data-stu-id="db5d7-102">Step 1: Configure Application Pool Identity</span></span>
<span data-ttu-id="db5d7-103">在本教程中，你可以使用应用程序池在 Microsoft Internet 信息服务 (IIS) 来处理业务流程发布为 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="db5d7-103">In this tutorial, you use an application pool in Microsoft Internet Information Services (IIS) to process the orchestration, which you publish as a Web service.</span></span> <span data-ttu-id="db5d7-104">应用程序池是由工作进程提供服务的一个或多个 Url 的分组。</span><span class="sxs-lookup"><span data-stu-id="db5d7-104">An application pool is a grouping of one or more URLs served by a worker process.</span></span>  

 <span data-ttu-id="db5d7-105">应用程序池标识是在其下运行的应用程序池辅助进程的服务帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="db5d7-105">The identity of an application pool is the name of the service account under which the worker process of the application pool runs.</span></span> <span data-ttu-id="db5d7-106">默认情况下，应用程序池具有低级别的用户访问权限并且是本教程中对函数没有足够的网络服务用户帐户下运行。</span><span class="sxs-lookup"><span data-stu-id="db5d7-106">By default, application pools operate under the Network Service user account, which has low-level user-access rights and is insufficient for this tutorial to function.</span></span> <span data-ttu-id="db5d7-107">出于安全原因，你想要配置应用程序池标识设置为用户帐户的绝对最低权限，但在最少的权限写入到 MessageBox (BizTalkMsgBoxDb) 数据库和配置数据库 (也称为 BizTalk管理数据库中，或 BizTalkMgmtDb）。</span><span class="sxs-lookup"><span data-stu-id="db5d7-107">For security reasons, you want to configure the application pool identity to a user account with the absolute minimum permissions, but at least permissions to write to the MessageBox database (BizTalkMsgBoxDb) and Configuration database (also known as the BizTalk Management database, or BizTalkMgmtDb).</span></span>  

### <a name="to-change-the-service-account-under-which-an-application-pool-runs"></a><span data-ttu-id="db5d7-108">若要更改的应用程序池中运行的服务帐户</span><span class="sxs-lookup"><span data-stu-id="db5d7-108">To change the service account under which an application pool runs</span></span>  

1. <span data-ttu-id="db5d7-109">单击**启动**，依次指向**程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="db5d7-109">Click **Start**, point to **Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  

2. <span data-ttu-id="db5d7-110">在 Internet 信息服务 (IIS) 管理器中，展开本地计算机，然后展开**应用程序池**。</span><span class="sxs-lookup"><span data-stu-id="db5d7-110">In Internet Information Services (IIS) Manager, expand the local computer, and expand **Application Pools**.</span></span>  

3. <span data-ttu-id="db5d7-111">右键单击你想要配置的应用程序池 (默认情况下，在下运行此教程**DefaultAppPool**)，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="db5d7-111">Right-click the application pool you want to configure (by default, this tutorial runs under the **DefaultAppPool**), and then click **Properties**.</span></span>  

4. <span data-ttu-id="db5d7-112">DefaultAppPool 属性对话框中，在上**标识**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="db5d7-112">In the DefaultAppPool Properties dialog box, on the **Identity** tab, do the following:</span></span>  


   |     <span data-ttu-id="db5d7-113">使用此选项</span><span class="sxs-lookup"><span data-stu-id="db5d7-113">Use this</span></span>     |                                                                                                                                                                                                                                                                     <span data-ttu-id="db5d7-114">执行的操作</span><span class="sxs-lookup"><span data-stu-id="db5d7-114">To do this</span></span>                                                                                                                                                                                                                                                                      |
   |------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  <span data-ttu-id="db5d7-115">**预定义的**</span><span class="sxs-lookup"><span data-stu-id="db5d7-115">**Predefined**</span></span>  | <span data-ttu-id="db5d7-116">取消选中**预定义的**。</span><span class="sxs-lookup"><span data-stu-id="db5d7-116">Deselect **Predefined**.</span></span> <span data-ttu-id="db5d7-117">**预定义的**指的是标准的服务帐户，如下所示：</span><span class="sxs-lookup"><span data-stu-id="db5d7-117">**Predefined** refers to standard service accounts, such as the following:</span></span><br /><br /> <span data-ttu-id="db5d7-118">-   **网络服务**（默认值），其中包含可用于在远程计算机上的资源的访问权限的低级别的用户访问权限。</span><span class="sxs-lookup"><span data-stu-id="db5d7-118">-   **Network Service** (the default), which has low-level user access rights that can be used for access to resources on remote computers.</span></span><br /><span data-ttu-id="db5d7-119">-   **本地服务**，具有低级别的访问权限。</span><span class="sxs-lookup"><span data-stu-id="db5d7-119">-   **Local Service**, which has low-level access rights.</span></span> <span data-ttu-id="db5d7-120">对于不要求在远程计算机上的资源的访问权限的情况下使用此设置。</span><span class="sxs-lookup"><span data-stu-id="db5d7-120">You use this setting for situations that do not require access to resources on remote computers.</span></span><br /><span data-ttu-id="db5d7-121">-   **本地系统**，这是使用 Network Service 或 Local Service 帐户之外的更多的用户权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="db5d7-121">-   **Local System**, which is an account with more user rights than the Network Service or Local Service account.</span></span> |
   | <span data-ttu-id="db5d7-122">**可配置**</span><span class="sxs-lookup"><span data-stu-id="db5d7-122">**Configurable**</span></span> |                                                                                                                                                                                                                                     <span data-ttu-id="db5d7-123">选择**可配置**。</span><span class="sxs-lookup"><span data-stu-id="db5d7-123">Select **Configurable**.</span></span> <span data-ttu-id="db5d7-124">**可配置**指的是已注册的用户名。</span><span class="sxs-lookup"><span data-stu-id="db5d7-124">**Configurable** refers to registered user names.</span></span>                                                                                                                                                                                                                                      |
   |  <span data-ttu-id="db5d7-125">**用户名**</span><span class="sxs-lookup"><span data-stu-id="db5d7-125">**User name**</span></span>   |                                                                                                                                                                                                                                <span data-ttu-id="db5d7-126">键入要在其下运行辅助进程的帐户的用户名。</span><span class="sxs-lookup"><span data-stu-id="db5d7-126">Type the user name of the account under which you want the worker process to operate.</span></span>                                                                                                                                                                                                                                |
   |   <span data-ttu-id="db5d7-127">**密码**</span><span class="sxs-lookup"><span data-stu-id="db5d7-127">**Password**</span></span>   |                                                                                                                                                                                                                                                                 <span data-ttu-id="db5d7-128">键入密码。</span><span class="sxs-lookup"><span data-stu-id="db5d7-128">Type the password.</span></span>                                                                                                                                                                                                                                                                  |


5. <span data-ttu-id="db5d7-129">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="db5d7-129">Click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="db5d7-130">或者，为了提高安全性，可以创建在你创建具备定制为本教程的权限的自定义标识下运行的全新应用程序池。</span><span class="sxs-lookup"><span data-stu-id="db5d7-130">Alternatively, for increased security, you could create an entirely new application pool that runs under a custom identity that you create with permissions tailored for this tutorial.</span></span>  

   <span data-ttu-id="db5d7-131">请继续执行[步骤 2： 创建一个新项目](../../adapters-and-accelerators/accelerator-hl7/step-2-create-a-new-project.md)。</span><span class="sxs-lookup"><span data-stu-id="db5d7-131">Proceed to [Step 2: Create a New Project](../../adapters-and-accelerators/accelerator-hl7/step-2-create-a-new-project.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="db5d7-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="db5d7-132">See Also</span></span>  
 [<span data-ttu-id="db5d7-133">消息充实教程</span><span class="sxs-lookup"><span data-stu-id="db5d7-133">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)