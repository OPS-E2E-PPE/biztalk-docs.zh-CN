---
title: "如何维护词汇版本 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, vocabularies
- vocabularies, creating
- vocabularies, versioning
- vocabularies, publishing
- versioning, vocabularies
- updating, vocabularies
- vocabularies, updating
ms.assetid: 43593c6f-4590-4940-ac17-4015928e5838
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b3c67d79878c59e3b0dcba6dcd15955f34ad97c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-maintain-vocabulary-versions"></a><span data-ttu-id="b45da-102">如何维护词汇版本</span><span class="sxs-lookup"><span data-stu-id="b45da-102">How to Maintain Vocabulary Versions</span></span>
<span data-ttu-id="b45da-103">在向某个版本的词汇中添加了词汇定义之后，可以将该版本保存到规则存储中以用于以后的开发，也可以发布该版本以创建明确定义的不可变数据绑定术语集，用户在开发策略时，可以向规则中添加这些数据绑定术语。</span><span class="sxs-lookup"><span data-stu-id="b45da-103">When you have added vocabulary definitions to a version of your vocabulary, you can save the version to the rule store for further development, or you can publish the version to create a well-defined, immutable set of data-bound terms that are available to users to add to rules as they develop their policies.</span></span> <span data-ttu-id="b45da-104">请注意，现有规则将仍指向旧版本。</span><span class="sxs-lookup"><span data-stu-id="b45da-104">Note that fact that existing rules will still point to the old versions.</span></span>  
  
 <span data-ttu-id="b45da-105">本主题包含以下任务的过程：</span><span class="sxs-lookup"><span data-stu-id="b45da-105">This topic contains procedures for the following tasks:</span></span>  
  
-   <span data-ttu-id="b45da-106">若要保存词汇版本</span><span class="sxs-lookup"><span data-stu-id="b45da-106">To save a vocabulary version</span></span>  
  
-   <span data-ttu-id="b45da-107">要发布的词汇版本</span><span class="sxs-lookup"><span data-stu-id="b45da-107">To publish a vocabulary version</span></span>  
  
-   <span data-ttu-id="b45da-108">若要创建词汇的更新的版本</span><span class="sxs-lookup"><span data-stu-id="b45da-108">To create an updated version of a vocabulary</span></span>  
  
-   <span data-ttu-id="b45da-109">若要创建空的新版本的词汇</span><span class="sxs-lookup"><span data-stu-id="b45da-109">To create an empty new version of a vocabulary</span></span>  
  
### <a name="to-save-a-vocabulary-version"></a><span data-ttu-id="b45da-110">若要保存词汇版本</span><span class="sxs-lookup"><span data-stu-id="b45da-110">To save a vocabulary version</span></span>  
  
-   <span data-ttu-id="b45da-111">右键单击版本，并依次**保存**。</span><span class="sxs-lookup"><span data-stu-id="b45da-111">Right-click the version, and then click **Save**.</span></span>  
  
### <a name="to-publish-a-vocabulary-version"></a><span data-ttu-id="b45da-112">要发布的词汇版本</span><span class="sxs-lookup"><span data-stu-id="b45da-112">To publish a vocabulary version</span></span>  
  
-   <span data-ttu-id="b45da-113">右键单击版本，并依次**发布**。</span><span class="sxs-lookup"><span data-stu-id="b45da-113">Right-click the version, and then click **Publish**.</span></span>  
  
### <a name="to-create-an-updated-version-of-a-vocabulary"></a><span data-ttu-id="b45da-114">若要创建词汇的更新的版本</span><span class="sxs-lookup"><span data-stu-id="b45da-114">To create an updated version of a vocabulary</span></span>  
  
1.  <span data-ttu-id="b45da-115">右键单击现有版本，并依次**复制**。</span><span class="sxs-lookup"><span data-stu-id="b45da-115">Right-click an existing version, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="b45da-116">右键单击词汇文件夹中，并依次**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="b45da-116">Right-click the vocabulary folder, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="b45da-117">使用与复制的版本相同的元素，创建新的版本。</span><span class="sxs-lookup"><span data-stu-id="b45da-117">A new version is created, with the same elements as the copied version.</span></span>  
  
### <a name="to-create-an-empty-new-version-of-a-vocabulary"></a><span data-ttu-id="b45da-118">若要创建空的新版本的词汇</span><span class="sxs-lookup"><span data-stu-id="b45da-118">To create an empty new version of a vocabulary</span></span>  
  
-   <span data-ttu-id="b45da-119">右键单击词汇文件夹中，并依次**添加新版本**。</span><span class="sxs-lookup"><span data-stu-id="b45da-119">Right-click the vocabulary folder, and then click **Add New Version**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b45da-120">只能使用已发布的词汇中的词汇定义。</span><span class="sxs-lookup"><span data-stu-id="b45da-120">You can only use vocabulary definitions from published vocabularies.</span></span>