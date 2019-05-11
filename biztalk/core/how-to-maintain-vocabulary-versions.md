---
title: 如何维护词汇版本 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a3049a0e14ad24b31f172a1c49189f968b6dabd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384700"
---
# <a name="how-to-maintain-vocabulary-versions"></a><span data-ttu-id="79d4b-102">如何维护词汇版本</span><span class="sxs-lookup"><span data-stu-id="79d4b-102">How to Maintain Vocabulary Versions</span></span>
<span data-ttu-id="79d4b-103">当词汇定义添加到版本的词汇后时，可以将该版本保存到规则存储中供进一步开发，也可以发布要创建可供用户若要添加的数据绑定术语的定义完善且不可变集的版本规则开发其策略。</span><span class="sxs-lookup"><span data-stu-id="79d4b-103">When you have added vocabulary definitions to a version of your vocabulary, you can save the version to the rule store for further development, or you can publish the version to create a well-defined, immutable set of data-bound terms that are available to users to add to rules as they develop their policies.</span></span> <span data-ttu-id="79d4b-104">请注意，现有的规则仍指向旧版本这一事实。</span><span class="sxs-lookup"><span data-stu-id="79d4b-104">Note that fact that existing rules will still point to the old versions.</span></span>  
  
 <span data-ttu-id="79d4b-105">本主题包含以下任务的过程：</span><span class="sxs-lookup"><span data-stu-id="79d4b-105">This topic contains procedures for the following tasks:</span></span>  
  
-   <span data-ttu-id="79d4b-106">若要保存词汇版本</span><span class="sxs-lookup"><span data-stu-id="79d4b-106">To save a vocabulary version</span></span>  
  
-   <span data-ttu-id="79d4b-107">若要发布的词汇版本</span><span class="sxs-lookup"><span data-stu-id="79d4b-107">To publish a vocabulary version</span></span>  
  
-   <span data-ttu-id="79d4b-108">若要创建某一词汇的更新的版本</span><span class="sxs-lookup"><span data-stu-id="79d4b-108">To create an updated version of a vocabulary</span></span>  
  
-   <span data-ttu-id="79d4b-109">若要创建一个空的新版本的词汇</span><span class="sxs-lookup"><span data-stu-id="79d4b-109">To create an empty new version of a vocabulary</span></span>  
  
### <a name="to-save-a-vocabulary-version"></a><span data-ttu-id="79d4b-110">若要保存词汇版本</span><span class="sxs-lookup"><span data-stu-id="79d4b-110">To save a vocabulary version</span></span>  
  
-   <span data-ttu-id="79d4b-111">右键单击该版本，然后依次**保存**。</span><span class="sxs-lookup"><span data-stu-id="79d4b-111">Right-click the version, and then click **Save**.</span></span>  
  
### <a name="to-publish-a-vocabulary-version"></a><span data-ttu-id="79d4b-112">若要发布的词汇版本</span><span class="sxs-lookup"><span data-stu-id="79d4b-112">To publish a vocabulary version</span></span>  
  
-   <span data-ttu-id="79d4b-113">右键单击该版本，然后依次**发布**。</span><span class="sxs-lookup"><span data-stu-id="79d4b-113">Right-click the version, and then click **Publish**.</span></span>  
  
### <a name="to-create-an-updated-version-of-a-vocabulary"></a><span data-ttu-id="79d4b-114">若要创建某一词汇的更新的版本</span><span class="sxs-lookup"><span data-stu-id="79d4b-114">To create an updated version of a vocabulary</span></span>  
  
1.  <span data-ttu-id="79d4b-115">右键单击现有版本，然后依次**复制**。</span><span class="sxs-lookup"><span data-stu-id="79d4b-115">Right-click an existing version, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="79d4b-116">右键单击词汇文件夹，然后依次**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="79d4b-116">Right-click the vocabulary folder, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="79d4b-117">创建一个新版本，具有与复制的版本相同的元素。</span><span class="sxs-lookup"><span data-stu-id="79d4b-117">A new version is created, with the same elements as the copied version.</span></span>  
  
### <a name="to-create-an-empty-new-version-of-a-vocabulary"></a><span data-ttu-id="79d4b-118">若要创建一个空的新版本的词汇</span><span class="sxs-lookup"><span data-stu-id="79d4b-118">To create an empty new version of a vocabulary</span></span>  
  
-   <span data-ttu-id="79d4b-119">右键单击词汇文件夹，然后依次**添加新版本**。</span><span class="sxs-lookup"><span data-stu-id="79d4b-119">Right-click the vocabulary folder, and then click **Add New Version**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="79d4b-120">您只能使用已发布的词汇中的词汇定义。</span><span class="sxs-lookup"><span data-stu-id="79d4b-120">You can only use vocabulary definitions from published vocabularies.</span></span>