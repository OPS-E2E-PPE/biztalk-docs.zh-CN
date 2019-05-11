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
# <a name="how-the-remove-namespace-sample-works"></a>删除 Namespace 示例工作原理
第二个和第三个测试使用**删除 Namespace**组件位于**NamespaceSampleSendPipeline**管道。 它将作为输入具有对根节点，如下所示的命名空间的文档：  
  
```  
<ns0:CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1"   
    Status="Status_2"   
    xmlns:ns0="http://schemas.microsoft.biztalk.esb.test.com/test">  
```  
  
 **删除 Namespace**组件只需删除此命名空间，并返回不具有根节点命名空间中，一个文档，如下所示：  
  
```  
<CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1" Status="Status_2">  
```