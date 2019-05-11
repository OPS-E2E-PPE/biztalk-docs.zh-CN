---
title: 创建和修改 BizTalk 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], modifying
- managing [applications], creating
- applications, modifying
- applications, creating
- modifying, applications
- creating, applications
ms.assetid: d6c9ff3a-3903-40ec-bcaa-e46cbaf8a58d
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79724d74baf3a5cddee910e7144c06c94680ac17
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353777"
---
# <a name="creating-and-modifying-biztalk-applications"></a><span data-ttu-id="14571-102">创建和修改 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="14571-102">Creating and Modifying BizTalk Applications</span></span>
<span data-ttu-id="14571-103">本部分介绍如何使用 BizTalk Server 管理控制台或 BTSTask 命令行工具来创建、 配置和修改 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="14571-103">This section describes how to use the BizTalk Server Administration console or the BTSTask command-line tool to create, configure, and modify BizTalk applications.</span></span>  
  
 <span data-ttu-id="14571-104">有关创建背景信息，管理、 部署和更新 BizTalk 应用程序，请参阅[了解 BizTalk 应用程序部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)。</span><span class="sxs-lookup"><span data-stu-id="14571-104">For background information on creating, managing, deploying, and updating BizTalk applications, see [Understanding BizTalk Application Deployment and Management](../core/understanding-biztalk-application-deployment-and-management.md).</span></span> <span data-ttu-id="14571-105">有关管理项目，包括编辑其属性，请参阅[管理项目](../core/managing-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="14571-105">For information about managing artifacts, including editing their properties, see [Managing Artifacts](../core/managing-artifacts.md).</span></span> <span data-ttu-id="14571-106">有关部署 BizTalk 应用程序的说明，请参阅[部署 BizTalk 应用程序](../core/deploying-biztalk-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="14571-106">For instructions on deploying BizTalk applications, see [Deploying BizTalk Applications](../core/deploying-biztalk-applications.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="14571-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="14571-107">In This Section</span></span>  
  
-   [<span data-ttu-id="14571-108">如何创建应用程序</span><span class="sxs-lookup"><span data-stu-id="14571-108">How to Create an Application</span></span>](../core/how-to-create-an-application.md)  
  
-   [<span data-ttu-id="14571-109">如何配置应用程序</span><span class="sxs-lookup"><span data-stu-id="14571-109">How to Configure an Application</span></span>](../core/how-to-configure-an-application.md)  
  
-   [<span data-ttu-id="14571-110">如何更改应用程序的名称</span><span class="sxs-lookup"><span data-stu-id="14571-110">How to Change the Name of an Application</span></span>](../core/how-to-change-the-name-of-an-application.md)  
  
-   [<span data-ttu-id="14571-111">如何创建或添加项目</span><span class="sxs-lookup"><span data-stu-id="14571-111">How to Create or Add an Artifact</span></span>](../core/how-to-create-or-add-an-artifact.md)  
  
-   [<span data-ttu-id="14571-112">如何链接到一个自述文件</span><span class="sxs-lookup"><span data-stu-id="14571-112">How to Link to a Readme File</span></span>](../core/how-to-link-to-a-readme-file.md)  
  
-   [<span data-ttu-id="14571-113">如何将一个 64 位项目添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="14571-113">How to Add a 64-Bit Artifact to an Application</span></span>](../core/how-to-add-a-64-bit-artifact-to-an-application.md)  
  
-   [<span data-ttu-id="14571-114">如何更改默认应用程序</span><span class="sxs-lookup"><span data-stu-id="14571-114">How to Change the Default Application</span></span>](../core/how-to-change-the-default-application.md)  
  
-   [<span data-ttu-id="14571-115">如何添加对另一个应用程序的引用</span><span class="sxs-lookup"><span data-stu-id="14571-115">How to Add a Reference to Another Application</span></span>](../core/how-to-add-a-reference-to-another-application.md)  
  
-   [<span data-ttu-id="14571-116">如何查看应用程序的引用</span><span class="sxs-lookup"><span data-stu-id="14571-116">How to View the References of an Application</span></span>](../core/how-to-view-the-references-of-an-application.md)  
  
-   [<span data-ttu-id="14571-117">如何删除对另一个应用程序的引用</span><span class="sxs-lookup"><span data-stu-id="14571-117">How to Remove a Reference to Another Application</span></span>](../core/how-to-remove-a-reference-to-another-application.md)  
  
-   [<span data-ttu-id="14571-118">如何将项目移到不同的应用程序</span><span class="sxs-lookup"><span data-stu-id="14571-118">How to Move an Artifact to a Different Application</span></span>](../core/how-to-move-an-artifact-to-a-different-application.md)  
  
-   [<span data-ttu-id="14571-119">如何从应用程序中删除项目</span><span class="sxs-lookup"><span data-stu-id="14571-119">How to Remove an Artifact from an Application</span></span>](../core/how-to-remove-an-artifact-from-an-application.md)