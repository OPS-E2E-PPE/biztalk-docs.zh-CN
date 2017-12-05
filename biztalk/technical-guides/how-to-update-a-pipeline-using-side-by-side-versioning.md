---
title: "如何更新管道使用的并行版本控制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd884a76-71dd-4c90-b4ba-f1cd7f48eb04
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a5b977d8f0d1964df33c2b2f549bd420d0d3179
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-update-a-pipeline-using-side-by-side-versioning"></a><span data-ttu-id="1508f-102">如何更新管道使用的并行版本控制</span><span class="sxs-lookup"><span data-stu-id="1508f-102">How to Update a Pipeline Using Side-by-Side Versioning</span></span>
<span data-ttu-id="1508f-103">若要使用的并行版本控制添加一条新管道的简单方法是在发送端口中选择新部署的管道版本或者接收位置。</span><span class="sxs-lookup"><span data-stu-id="1508f-103">The simple way to use a new pipeline added by side-by-side versioning is to select the newly deployed pipeline version in the send port or receive location.</span></span> <span data-ttu-id="1508f-104">这将替换为新替换旧的管道。</span><span class="sxs-lookup"><span data-stu-id="1508f-104">This will replace the old pipeline with the new one.</span></span> <span data-ttu-id="1508f-105">但是，如果你需要 true 的并行功能用于获取向后兼容性，然后必须创建新的发送端口和接收位置并将其绑定到指定的新管道版本。</span><span class="sxs-lookup"><span data-stu-id="1508f-105">However, if you need true side-by-side functionality for backwards-compatibility, then you must create new send ports and receive locations and bind them to the new pipeline version specified.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1508f-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="1508f-106">Prerequisites</span></span>  
 <span data-ttu-id="1508f-107">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="1508f-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-add-a-new-version-of-a-pipeline-component"></a><span data-ttu-id="1508f-108">若要添加管道组件的新版本</span><span class="sxs-lookup"><span data-stu-id="1508f-108">To add a new version of a pipeline component</span></span>  
  
1.  <span data-ttu-id="1508f-109">在 Visual Studio 中，创建管道组件的新版本，并且对程序集签名。</span><span class="sxs-lookup"><span data-stu-id="1508f-109">In Visual Studio, create a new version of the pipeline component, and sign the assembly.</span></span>  
  
2.  <span data-ttu-id="1508f-110">添加中的管道组件**管道组件**文件夹 (\<*安装文件夹*\>\Pipeline 组件)。</span><span class="sxs-lookup"><span data-stu-id="1508f-110">Add the pipeline component in the **Pipeline Components** folder (\<*installation folder*\>\Pipeline Components).</span></span>  
  
3.  <span data-ttu-id="1508f-111">将管道组件添加到管道。</span><span class="sxs-lookup"><span data-stu-id="1508f-111">Add the pipeline component to your pipeline.</span></span>  
  
4.  <span data-ttu-id="1508f-112">生成管道或将部署你的解决方案后, 删除管道组件从**管道组件**文件夹。</span><span class="sxs-lookup"><span data-stu-id="1508f-112">After building the pipeline or deploying your solution, remove the pipeline component from the **Pipeline Components** folder.</span></span>  
  
5.  <span data-ttu-id="1508f-113">将管道组件添加到全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="1508f-113">Add the pipeline component to the global assembly cache (GAC).</span></span>  
  
 <span data-ttu-id="1508f-114">完成这些步骤后，已编译的管道程序集将引用的管道组件的正确版本和 BizTalk Server 使用的应用程序域将在 GAC 中，而不是查找上一个查找管道组件的新版本管道组件文件夹中的管道组件的版本。</span><span class="sxs-lookup"><span data-stu-id="1508f-114">After you have completed these steps, the compiled pipeline assembly will refer to the correct version of the pipeline component, and the AppDomain used by BizTalk Server will find the new version of the pipeline component in the GAC, rather than finding the previous version of the pipeline component in the Pipeline Components folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1508f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1508f-115">See Also</span></span>  
 [<span data-ttu-id="1508f-116">更新正在使用的并排版本控制</span><span class="sxs-lookup"><span data-stu-id="1508f-116">Updating Using Side-by-Side Versioning</span></span>](../technical-guides/updating-using-side-by-side-versioning.md)