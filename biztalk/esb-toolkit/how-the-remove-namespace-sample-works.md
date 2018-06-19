---
title: 删除 Namespace 示例的工作原理 |Microsoft 文档
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
ms.openlocfilehash: e82e4f369d8db2230b44586cbb928ea57b27f462
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294517"
---
# <a name="how-the-remove-namespace-sample-works"></a>删除 Namespace 示例的工作原理
第二个和第三个测试使用**删除 Namespace**组件位于**NamespaceSampleSendPipeline**管道。 它将作为输入具有上的根节点，如下所示的命名空间的文档：  
  
```  
<ns0:CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1"   
    Status="Status_2"   
    xmlns:ns0="http://schemas.microsoft.biztalk.esb.test.com/test">  
```  
  
 **删除 Namespace**组件只需删除此命名空间，并返回不具有根节点命名空间中，一个文档，如下所示：  
  
```  
<CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1" Status="Status_2">  
```