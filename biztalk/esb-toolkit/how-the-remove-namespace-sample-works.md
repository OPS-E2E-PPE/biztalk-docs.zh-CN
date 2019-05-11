---
title: 删除 Namespace 示例工作原理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf5834b4-e0fd-4180-9d15-4cdd99f0f353
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9fc0c3accdf81322a08562bd186417421c10c50
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279013"
---
# <a name="how-the-remove-namespace-sample-works"></a><span data-ttu-id="8a1c6-102">删除 Namespace 示例工作原理</span><span class="sxs-lookup"><span data-stu-id="8a1c6-102">How the Remove Namespace Sample Works</span></span>
<span data-ttu-id="8a1c6-103">第二个和第三个测试使用**删除 Namespace**组件位于**NamespaceSampleSendPipeline**管道。</span><span class="sxs-lookup"><span data-stu-id="8a1c6-103">The second and third tests use the **Remove Namespace** component located in the **NamespaceSampleSendPipeline** pipeline.</span></span> <span data-ttu-id="8a1c6-104">它将作为输入具有对根节点，如下所示的命名空间的文档：</span><span class="sxs-lookup"><span data-stu-id="8a1c6-104">It takes as input a document with a namespace on the root node, such as the following:</span></span>  
  
```  
<ns0:CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1"   
    Status="Status_2"   
    xmlns:ns0="http://schemas.microsoft.biztalk.esb.test.com/test">  
```  
  
 <span data-ttu-id="8a1c6-105">**删除 Namespace**组件只需删除此命名空间，并返回不具有根节点命名空间中，一个文档，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8a1c6-105">The **Remove Namespace** component simply removes this namespace and returns a document that does not have a root node namespace, as shown here:</span></span>  
  
```  
<CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1" Status="Status_2">  
```