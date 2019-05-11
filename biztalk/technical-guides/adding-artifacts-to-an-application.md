---
title: 将项目添加到应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a9b5e92e-2e55-41d7-9959-f62753bbeb04
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ac647201a834d90d745564076b040954c1c3667
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401411"
---
# <a name="adding-artifacts-to-an-application"></a><span data-ttu-id="348d8-102">将项目添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="348d8-102">Adding Artifacts to an Application</span></span>
<span data-ttu-id="348d8-103">可以添加和配置项目，例如发送和接收端口、 接收位置和业务流程，使用管理控制台。</span><span class="sxs-lookup"><span data-stu-id="348d8-103">You can add and configure artifacts, such as send and receive ports, receive locations, and orchestrations, by using the Administration console.</span></span> <span data-ttu-id="348d8-104">您还可以生成绑定文件并将其添加到应用程序中，如果你想要应用于不同的环境，您将导入到应用程序的不同绑定。</span><span class="sxs-lookup"><span data-stu-id="348d8-104">You can also generate binding files and add them to the application if you want to apply different bindings for the different environments that you will import the application into.</span></span>  
  
 <span data-ttu-id="348d8-105">您可以添加其他 (通常非 BizTalk Server) 项目，如脚本、 证书和自述文件、 到资源节点下的应用程序。</span><span class="sxs-lookup"><span data-stu-id="348d8-105">You can add additional (typically non-BizTalk Server) artifacts, such as scripts, certificates, and Readme files, to the application under the Resources node.</span></span> <span data-ttu-id="348d8-106">若要执行此操作，使用管理控制台或 BTSTask。</span><span class="sxs-lookup"><span data-stu-id="348d8-106">To do so, use the Administration console or BTSTask.</span></span>  
  
 <span data-ttu-id="348d8-107">有关项目的详细信息，请参阅[如何创建或添加项目](http://go.microsoft.com/fwlink/?LinkID=154724)(http://go.microsoft.com/fwlink/?LinkID=154724)，[管理项目](http://go.microsoft.com/fwlink/?LinkID=154725)(http://go.microsoft.com/fwlink/?LinkID=154725)和[绑定文件和应用程序部署](http://go.microsoft.com/fwlink/?LinkID=154726) (http://go.microsoft.com/fwlink/?LinkID=154726).</span><span class="sxs-lookup"><span data-stu-id="348d8-107">For more information about artifacts, see [How to Create or Add an Artifact](http://go.microsoft.com/fwlink/?LinkID=154724) (http://go.microsoft.com/fwlink/?LinkID=154724), [Managing Artifacts](http://go.microsoft.com/fwlink/?LinkID=154725) (http://go.microsoft.com/fwlink/?LinkID=154725) and [Binding Files and Application Deployment](http://go.microsoft.com/fwlink/?LinkID=154726) (http://go.microsoft.com/fwlink/?LinkID=154726).</span></span>  
  
## <a name="factoring-artifacts-into-multiple-biztalk-applications"></a><span data-ttu-id="348d8-108">分解为多个 BizTalk 应用程序的项目</span><span class="sxs-lookup"><span data-stu-id="348d8-108">Factoring Artifacts into Multiple BizTalk Applications</span></span>  
 <span data-ttu-id="348d8-109">在开发过程中，你可能已部署您的程序集到单一应用程序中为方便起见。</span><span class="sxs-lookup"><span data-stu-id="348d8-109">During the development process, you may have deployed your assemblies into a single application for convenience.</span></span> <span data-ttu-id="348d8-110">由于各种原因，你可能想要部署到生产环境之前，将项目分解到多个应用程序。</span><span class="sxs-lookup"><span data-stu-id="348d8-110">For various reasons, you may want to factor the artifacts into multiple applications before they are deployed into production.</span></span>  
  
 <span data-ttu-id="348d8-111">在部署之前，应执行程序集的分解情况的深入的分析。</span><span class="sxs-lookup"><span data-stu-id="348d8-111">Before deploying, you should perform an in-depth analysis of the factoring of an assembly.</span></span> <span data-ttu-id="348d8-112">确定是否应执行任何分解、 完整分解或者最佳分解。</span><span class="sxs-lookup"><span data-stu-id="348d8-112">Determine whether you should perform No factoring, Full factoring, or Optimal factoring.</span></span>  
  
 <span data-ttu-id="348d8-113">**没有分解**</span><span class="sxs-lookup"><span data-stu-id="348d8-113">**No Factoring**</span></span>  
  
 <span data-ttu-id="348d8-114">所有 BizTalk 项目都是在一个程序集中。</span><span class="sxs-lookup"><span data-stu-id="348d8-114">All BizTalk artifacts are in one assembly.</span></span> <span data-ttu-id="348d8-115">这是最容易了解和部署，但可以最大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="348d8-115">This is the easiest to understand and deploy, but provides the least amount of flexibility.</span></span>  
  
 <span data-ttu-id="348d8-116">**完整分解**</span><span class="sxs-lookup"><span data-stu-id="348d8-116">**Full Factoring**</span></span>  
  
 <span data-ttu-id="348d8-117">每个 BizTalk 项目是在自己的程序集。</span><span class="sxs-lookup"><span data-stu-id="348d8-117">Each BizTalk artifact is in its own assembly.</span></span> <span data-ttu-id="348d8-118">这提供了最大的灵活性，但最复杂部署和了解。</span><span class="sxs-lookup"><span data-stu-id="348d8-118">This provides the most flexibility, but is the most complex to deploy and understand.</span></span>  
  
 <span data-ttu-id="348d8-119">**最佳分解**</span><span class="sxs-lookup"><span data-stu-id="348d8-119">**Optimal Factoring**</span></span>  
  
 <span data-ttu-id="348d8-120">最佳分解介于之间无分解和完整分解基于 BizTalk 应用程序的深入分析。</span><span class="sxs-lookup"><span data-stu-id="348d8-120">Optimal factoring falls between No Factoring and Full Factoring based on in-depth analysis of your BizTalk applications.</span></span> <span data-ttu-id="348d8-121">除了版本控制，这样，您可以更轻松地实现您的 BizTalk 主机设计。</span><span class="sxs-lookup"><span data-stu-id="348d8-121">In addition to versioning, this allows you to more easily implement your BizTalk host design.</span></span> <span data-ttu-id="348d8-122">这被通过查找 BizTalk 项目之间的关系。</span><span class="sxs-lookup"><span data-stu-id="348d8-122">This is achieved by looking for relationships among BizTalk artifacts.</span></span> <span data-ttu-id="348d8-123">如果可能，将始终在同一程序集版本控制的项目。</span><span class="sxs-lookup"><span data-stu-id="348d8-123">If possible, put artifacts that are always versioned together in the same assembly.</span></span> <span data-ttu-id="348d8-124">如果需要独立的版本控制的项目，然后它们必须放入不同的程序集。</span><span class="sxs-lookup"><span data-stu-id="348d8-124">If independent versioning of the artifacts is required, then they must be put in different assemblies.</span></span> <span data-ttu-id="348d8-125">这是你想要实现的分解级别。</span><span class="sxs-lookup"><span data-stu-id="348d8-125">This is the level of factoring that you want to achieve.</span></span>