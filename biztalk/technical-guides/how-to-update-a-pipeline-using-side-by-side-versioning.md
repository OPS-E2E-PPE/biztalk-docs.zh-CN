---
title: 如何更新使用的并行版本控制的管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd884a76-71dd-4c90-b4ba-f1cd7f48eb04
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85aa5f7d134e14d16fbb4fb88fcff29cf6ce672f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400273"
---
# <a name="how-to-update-a-pipeline-using-side-by-side-versioning"></a><span data-ttu-id="5a409-102">如何更新使用的并行版本控制的管道</span><span class="sxs-lookup"><span data-stu-id="5a409-102">How to Update a Pipeline Using Side-by-Side Versioning</span></span>
<span data-ttu-id="5a409-103">使用新的管道的并行版本控制添加的简单方法是选择新部署的管道版本中的发送端口或接收位置。</span><span class="sxs-lookup"><span data-stu-id="5a409-103">The simple way to use a new pipeline added by side-by-side versioning is to select the newly deployed pipeline version in the send port or receive location.</span></span> <span data-ttu-id="5a409-104">这将使用新替换旧的管道。</span><span class="sxs-lookup"><span data-stu-id="5a409-104">This will replace the old pipeline with the new one.</span></span> <span data-ttu-id="5a409-105">但是，如果用于向后兼容性需要真正的并行功能，然后你必须创建新发送端口和接收位置并将其绑定到指定的新管道版本。</span><span class="sxs-lookup"><span data-stu-id="5a409-105">However, if you need true side-by-side functionality for backwards-compatibility, then you must create new send ports and receive locations and bind them to the new pipeline version specified.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5a409-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="5a409-106">Prerequisites</span></span>  
 <span data-ttu-id="5a409-107">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="5a409-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-add-a-new-version-of-a-pipeline-component"></a><span data-ttu-id="5a409-108">若要添加管道组件的新版本</span><span class="sxs-lookup"><span data-stu-id="5a409-108">To add a new version of a pipeline component</span></span>  
  
1. <span data-ttu-id="5a409-109">在 Visual Studio 中创建的管道组件的新版本和程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="5a409-109">In Visual Studio, create a new version of the pipeline component, and sign the assembly.</span></span>  
  
2. <span data-ttu-id="5a409-110">将管道组件中的添加**管道组件**文件夹 (\<*安装文件夹*\>\Pipeline 组件)。</span><span class="sxs-lookup"><span data-stu-id="5a409-110">Add the pipeline component in the **Pipeline Components** folder (\<*installation folder*\>\Pipeline Components).</span></span>  
  
3. <span data-ttu-id="5a409-111">将管道组件添加到你的管道。</span><span class="sxs-lookup"><span data-stu-id="5a409-111">Add the pipeline component to your pipeline.</span></span>  
  
4. <span data-ttu-id="5a409-112">生成管道或部署你的解决方案之后, 删除从管道组件**管道组件**文件夹。</span><span class="sxs-lookup"><span data-stu-id="5a409-112">After building the pipeline or deploying your solution, remove the pipeline component from the **Pipeline Components** folder.</span></span>  
  
5. <span data-ttu-id="5a409-113">管道组件添加到全局程序集缓存 (GAC)。</span><span class="sxs-lookup"><span data-stu-id="5a409-113">Add the pipeline component to the global assembly cache (GAC).</span></span>  
  
   <span data-ttu-id="5a409-114">完成这些步骤后，已编译的管道程序集将引用的管道组件的正确版本和 BizTalk Server 使用的应用程序域将在 GAC 中，而不是查找上一个查找管道组件的新版本管道组件文件夹中的管道组件的版本。</span><span class="sxs-lookup"><span data-stu-id="5a409-114">After you have completed these steps, the compiled pipeline assembly will refer to the correct version of the pipeline component, and the AppDomain used by BizTalk Server will find the new version of the pipeline component in the GAC, rather than finding the previous version of the pipeline component in the Pipeline Components folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a409-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a409-115">See Also</span></span>  
 [<span data-ttu-id="5a409-116">更新正在使用的并排版本控制</span><span class="sxs-lookup"><span data-stu-id="5a409-116">Updating Using Side-by-Side Versioning</span></span>](../technical-guides/updating-using-side-by-side-versioning.md)