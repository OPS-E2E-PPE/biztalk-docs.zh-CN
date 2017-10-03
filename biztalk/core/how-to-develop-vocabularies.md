---
title: "如何开发词汇 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, vocabularies
- vocabularies, business rules
- business rules, vocabularies
- vocabularies, creating
ms.assetid: 5c16eb98-2257-44f2-8a29-899e02f7e556
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2644cc938cbe5e42f4e124453d863741755d965d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-develop-vocabularies"></a><span data-ttu-id="36745-102">如何开发词汇</span><span class="sxs-lookup"><span data-stu-id="36745-102">How to Develop Vocabularies</span></span>
<span data-ttu-id="36745-103">规则条件和操作基于源可能有详细说明，告知用户只需少量或者无有关它们的指的困难读取绑定信息。</span><span class="sxs-lookup"><span data-stu-id="36745-103">Rule conditions and actions are based on sources that may have detailed, difficult-to-read binding information that tells the user little or nothing about what they refer to.</span></span> <span data-ttu-id="36745-104">业务规则框架，可创建用于通过提供直观、 特定于域的用户可以将与规则条件和操作相关联的术语的用户简化的规则的开发的词汇。</span><span class="sxs-lookup"><span data-stu-id="36745-104">The Business Rules Framework enables you to create vocabularies to simplify the development of rules by offering users intuitive, domain-specific terminology that users can associate with rule conditions and actions.</span></span>  
  
 <span data-ttu-id="36745-105">你可以标识数据源以使用，创建新的词汇，并向它添加词汇定义。</span><span class="sxs-lookup"><span data-stu-id="36745-105">You can identify data sources to use, create a new vocabulary, and add vocabulary definitions to it.</span></span> <span data-ttu-id="36745-106">你可以将你词汇的版本保存到规则存储，并完成时，可以将其用户提供明确定义的、 不可变的一组绑定到数据引用的条款发布。</span><span class="sxs-lookup"><span data-stu-id="36745-106">You can save a version of your vocabulary to the rule store, and when it is complete, you can publish it to provide users with a well-defined, immutable set of terms that are bound to data references.</span></span>  
  
 <span data-ttu-id="36745-107">如果你需要在将来对你词汇进行更改，你可以只需创建反映所做的更改的词汇的新版本。</span><span class="sxs-lookup"><span data-stu-id="36745-107">If you need to make changes to your vocabulary in the future, you can simply create a new version of the vocabulary that reflects the changes.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="36745-108">创建新版本的词汇后，从早期版本生成的规则仍将指向以前的版本。</span><span class="sxs-lookup"><span data-stu-id="36745-108">When a new version of a vocabulary is created, the rules built from a previous version will still point to the previous version.</span></span>  
  
### <a name="to-create-a-vocabulary"></a><span data-ttu-id="36745-109">若要创建的词汇</span><span class="sxs-lookup"><span data-stu-id="36745-109">To create a vocabulary</span></span>  
  
1.  <span data-ttu-id="36745-110">在事实浏览器窗口中，单击**词汇**选项卡。</span><span class="sxs-lookup"><span data-stu-id="36745-110">In the Facts Explorer window, click the **Vocabularies** tab.</span></span>  
  
2.  <span data-ttu-id="36745-111">右键单击**词汇**文件夹，，然后单击**添加新词汇**。</span><span class="sxs-lookup"><span data-stu-id="36745-111">Right-click the **Vocabularies** folder, and then click **Add New Vocabulary**.</span></span>  
  
     <span data-ttu-id="36745-112">一个新**词汇**文件夹显示在**词汇**文件夹。</span><span class="sxs-lookup"><span data-stu-id="36745-112">A new **vocabulary** folder appears under the **Vocabularies** folder.</span></span>  
  
3.  <span data-ttu-id="36745-113">单击新建**词汇**文件夹，然后再编辑属性窗口中的名称。</span><span class="sxs-lookup"><span data-stu-id="36745-113">Click the new **vocabulary** folder, and then edit the name in the Properties window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="36745-114">你可以重命名词汇之前或策略，必须保存所有内容 （所有版本的工作定义）。</span><span class="sxs-lookup"><span data-stu-id="36745-114">You must save everything (all versions of the definitions) before you can rename a vocabulary or a policy.</span></span>