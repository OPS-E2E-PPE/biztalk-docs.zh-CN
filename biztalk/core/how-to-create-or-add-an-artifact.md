---
title: 如何创建或添加项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, artifacts
- artifacts, creating
- applications, artifacts
ms.assetid: fea7487c-b5fa-457f-8c74-a20ea3a6df85
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0d206566cf47363ab52b540a55a5a3bc0d5014c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339092"
---
# <a name="how-to-create-or-add-an-artifact"></a><span data-ttu-id="a56de-102">如何创建或添加项目</span><span class="sxs-lookup"><span data-stu-id="a56de-102">How to Create or Add an Artifact</span></span>
<span data-ttu-id="a56de-103">创建 BizTalk 应用程序后，可以从文件系统中添加基于文件的项目 （例如 BizTalk 程序集、.NET 程序集、 脚本和证书） 或从规则引擎数据库中添加策略。</span><span class="sxs-lookup"><span data-stu-id="a56de-103">After you create a BizTalk application, you can add file-based artifacts (for example BizTalk assemblies, .NET assemblies, scripts, and certificates) from the file system or add policies from the Rule Engine database.</span></span> <span data-ttu-id="a56de-104">此外可以创建发送端口、 发送端口组、 接收位置和接收应用程序中的端口。</span><span class="sxs-lookup"><span data-stu-id="a56de-104">You can also create send ports, send port groups, receive locations, and receive ports within the application.</span></span> <span data-ttu-id="a56de-105">创建或添加项目将它们添加到 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="a56de-105">Creating or adding artifacts adds them to the BizTalk Management database.</span></span> <span data-ttu-id="a56de-106">你可以随后部署该应用程序和其项目作为单个实体，如中所述[部署 BizTalk 应用程序](../core/deploying-biztalk-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="a56de-106">You can then deploy the application and its artifacts as a single entity, as described in [Deploying BizTalk Applications](../core/deploying-biztalk-applications.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a56de-107">某些类型的项目中必须是唯一的 BizTalk 应用程序或组。</span><span class="sxs-lookup"><span data-stu-id="a56de-107">Certain types of artifacts must be unique in a BizTalk application or group.</span></span> <span data-ttu-id="a56de-108">有关详细信息，请参阅[项目，必须是唯一的应用程序或组](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)。</span><span class="sxs-lookup"><span data-stu-id="a56de-108">For more information, see [Artifacts That Must Be Unique in an Application or Group](../core/artifacts-that-must-be-unique-in-an-application-or-group.md).</span></span>  
  
 <span data-ttu-id="a56de-109">添加或创建每个项目类型的过程，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="a56de-109">For procedures on adding or creating each artifact type, see the following topics:</span></span>  
  
-   [<span data-ttu-id="a56de-110">如何创建发送端口</span><span class="sxs-lookup"><span data-stu-id="a56de-110">How to Create a Send Port</span></span>](../core/how-to-create-a-send-port2.md)  
  
-   [<span data-ttu-id="a56de-111">如何创建发送端口组</span><span class="sxs-lookup"><span data-stu-id="a56de-111">How to Create a Send Port Group</span></span>](../core/how-to-create-a-send-port-group.md)  
  
-   [<span data-ttu-id="a56de-112">如何创建接收端口</span><span class="sxs-lookup"><span data-stu-id="a56de-112">How to Create a Receive Port</span></span>](../core/how-to-create-a-receive-port.md)  
  
-   [<span data-ttu-id="a56de-113">如何创建接收位置</span><span class="sxs-lookup"><span data-stu-id="a56de-113">How to Create a Receive Location</span></span>](../core/how-to-create-a-receive-location.md)  
  
-   [<span data-ttu-id="a56de-114">如何向应用程序添加策略</span><span class="sxs-lookup"><span data-stu-id="a56de-114">How to Add a Policy to an Application</span></span>](../core/how-to-add-a-policy-to-an-application.md)  
  
-   [<span data-ttu-id="a56de-115">如何将 BizTalk 程序集添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="a56de-115">How to Add a BizTalk Assembly to an Application</span></span>](../core/how-to-add-a-biztalk-assembly-to-an-application.md)  
  
-   [<span data-ttu-id="a56de-116">如何向应用程序添加预处理或后处理脚本</span><span class="sxs-lookup"><span data-stu-id="a56de-116">How to Add a Pre- or Post-processing Script to an Application</span></span>](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)  
  
-   [<span data-ttu-id="a56de-117">如何将文件添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="a56de-117">How to Add a File to an Application</span></span>](../core/how-to-add-a-file-to-an-application.md)  
  
-   [<span data-ttu-id="a56de-118">如何将证书添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="a56de-118">How to Add a Certificate to an Application</span></span>](../core/how-to-add-a-certificate-to-an-application.md)  
  
-   [<span data-ttu-id="a56de-119">如何向应用程序添加 COM 组件</span><span class="sxs-lookup"><span data-stu-id="a56de-119">How to Add a COM Component to an Application</span></span>](../core/how-to-add-a-com-component-to-an-application.md)  
  
-   [<span data-ttu-id="a56de-120">如何将.NET 程序集添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="a56de-120">How to Add a .NET Assembly to an Application</span></span>](../core/how-to-add-a-net-assembly-to-an-application.md)  
  
-   [<span data-ttu-id="a56de-121">如何向应用程序添加 BAM 项目</span><span class="sxs-lookup"><span data-stu-id="a56de-121">How to Add a BAM Artifact to an Application</span></span>](../core/how-to-add-a-bam-artifact-to-an-application.md)  
  
-   [<span data-ttu-id="a56de-122">如何将绑定文件添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="a56de-122">How to Add a Binding File to an Application</span></span>](../core/how-to-add-a-binding-file-to-an-application2.md)  
  
> [!NOTE]
>  <span data-ttu-id="a56de-123">如果要添加的项目具有很长的路径 （例如，路径和文件名称），要将项目添加到应用程序的操作可能会失败。</span><span class="sxs-lookup"><span data-stu-id="a56de-123">If the artifact you are adding has a very long path (e.g., the path and file name), the operation to add the artifact to an application may fail.</span></span> <span data-ttu-id="a56de-124">路径不能超过 260 个字符。</span><span class="sxs-lookup"><span data-stu-id="a56de-124">A path can't exceed 260 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a56de-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="a56de-125">See Also</span></span>  
 <span data-ttu-id="a56de-126">[创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="a56de-126">[Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="a56de-127">如何将一个 64 位项目添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="a56de-127">How to Add a 64-Bit Artifact to an Application</span></span>](../core/how-to-add-a-64-bit-artifact-to-an-application.md)