---
title: 如何修改词汇定义 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- vocabularies, facts
- modifying, vocabularies
- vocabularies, definitions
- vocabularies, modifying
ms.assetid: 866bb9b9-34e1-4a05-a84e-540c7f7fae3b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6aa62ebf0adda5798824003fa25cf1ed07b62932
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254165"
---
# <a name="how-to-modify-vocabulary-definitions"></a><span data-ttu-id="bf5d4-102">如何修改词汇定义</span><span class="sxs-lookup"><span data-stu-id="bf5d4-102">How to Modify Vocabulary Definitions</span></span>
<span data-ttu-id="bf5d4-103">通过使用词汇定义向导更改显示名称或更改与显示名称关联的绑定，可以修改未发布的词汇版本中的词汇定义。</span><span class="sxs-lookup"><span data-stu-id="bf5d4-103">You can modify a vocabulary definition in an unpublished version of a vocabulary by using the Vocabulary Definition Wizard to change the display name or to change the binding associated with the display name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf5d4-104">并非所有元素都可以修改。</span><span class="sxs-lookup"><span data-stu-id="bf5d4-104">Not all elements can be modified.</span></span>  
  
 <span data-ttu-id="bf5d4-105">本主题包含以下任务的过程：</span><span class="sxs-lookup"><span data-stu-id="bf5d4-105">This topic contains procedures for the following tasks:</span></span>  
  
-   <span data-ttu-id="bf5d4-106">修改词汇定义</span><span class="sxs-lookup"><span data-stu-id="bf5d4-106">To modify a vocabulary definition</span></span>  
  
-   <span data-ttu-id="bf5d4-107">向词汇或词汇定义添加事实</span><span class="sxs-lookup"><span data-stu-id="bf5d4-107">To add a fact to a vocabulary or vocabulary definition</span></span>  
  
### <a name="to-modify-a-vocabulary-definition"></a><span data-ttu-id="bf5d4-108">修改词汇定义</span><span class="sxs-lookup"><span data-stu-id="bf5d4-108">To modify a vocabulary definition</span></span>  
  
1.  <span data-ttu-id="bf5d4-109">右击词汇定义中，并依次**修改**。</span><span class="sxs-lookup"><span data-stu-id="bf5d4-109">Right-click the vocabulary definition, and then click **Modify**.</span></span>  
  
2.  <span data-ttu-id="bf5d4-110">只需像创建新的词汇定义一样使用词汇定义向导即可。</span><span class="sxs-lookup"><span data-stu-id="bf5d4-110">Use the Vocabulary Definition Wizard as you would to create a new vocabulary definition.</span></span>  
  
### <a name="to-add-a-fact-to-a-vocabulary-or-vocabulary-definition"></a><span data-ttu-id="bf5d4-111">向词汇或词汇定义添加事实</span><span class="sxs-lookup"><span data-stu-id="bf5d4-111">To add a fact to a vocabulary or vocabulary definition</span></span>  
  
1.  <span data-ttu-id="bf5d4-112">在事实浏览器窗口中，单击**词汇**选项卡，然后选择你想要更新的未发布的词汇版本。</span><span class="sxs-lookup"><span data-stu-id="bf5d4-112">In the Facts Explorer window, click the **Vocabularies** tab, and select the unpublished vocabulary version that you want to update.</span></span>  
  
2.  <span data-ttu-id="bf5d4-113">单击**数据库**， **XML 架构**，或 **.NET 类**。</span><span class="sxs-lookup"><span data-stu-id="bf5d4-113">Click **Databases**, **XML Schemas**, or **.NET Classes**.</span></span>  
  
3.  <span data-ttu-id="bf5d4-114">在数据源层次结构中导航到所需事实。</span><span class="sxs-lookup"><span data-stu-id="bf5d4-114">Navigate through the data source hierarchy to the fact you want.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bf5d4-115">该事实可以是数据库表或数据库表列，可以是 XML 文档元素或属性，也可以是 .NET 类或类成员。</span><span class="sxs-lookup"><span data-stu-id="bf5d4-115">The fact can be a database table or database table column, an XML document element or attribute, or a .NET class or class member.</span></span>  
  
4.  <span data-ttu-id="bf5d4-116">单击该事实并按住鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="bf5d4-116">Click the fact and hold down the mouse button.</span></span>  
  
5.  <span data-ttu-id="bf5d4-117">拖动事实**词汇**选项卡。</span><span class="sxs-lookup"><span data-stu-id="bf5d4-117">Drag the fact over the **Vocabularies** tab.</span></span>  
  
     <span data-ttu-id="bf5d4-118">**词汇**选项卡上打开。</span><span class="sxs-lookup"><span data-stu-id="bf5d4-118">The **Vocabularies** tab opens.</span></span>  
  
6.  <span data-ttu-id="bf5d4-119">将该事实拖至要修改的词汇版本。</span><span class="sxs-lookup"><span data-stu-id="bf5d4-119">Drag the fact to the vocabulary version you want to modify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf5d4-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf5d4-120">See Also</span></span>  
 [<span data-ttu-id="bf5d4-121">如何创建词汇定义</span><span class="sxs-lookup"><span data-stu-id="bf5d4-121">How to Create Vocabulary Definitions</span></span>](../core/how-to-create-vocabulary-definitions.md)