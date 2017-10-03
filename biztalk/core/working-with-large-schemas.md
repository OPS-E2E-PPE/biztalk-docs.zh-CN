---
title: "使用大型架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8348036d-6edb-46a3-badd-0223cfe0a92f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5c5ef679070009b5dfb5fdd403d238cfe243cb2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="working-with-large-schemas"></a>使用大型架构
当架构变得非常大时，您可能会发现刷新 XSD 视图变得越来越慢，并且用户界面其他方面的响应也受到影响。 与此问题的解决方案是关闭自动刷新功能，并改为使用手动**刷新**XSD 视图定期刷新 XSD 视图中的链接。 有关分步说明有关如何启用自动刷新功能关闭，请参阅"打开和关闭的 XSD 视图自动刷新"的过程中[管理 XSD 视图](../core/how-to-manage-the-xsd-view.md)。  
  
 性能也会降低在大型架构中包含附加到多个根**架构**节点。 设置**根引用**属性可能会增加用户界面中的性能。 设置**根引用**能改善性能，因为编译器将为所有根架构创建 C# 类。 单个节点意味着创建更少的类。  
  
 **验证实例**可能会出现在用户界面中缓慢，由于验证始终按执行架构验证实例之前。 架构验证仅发生在用户界面中。 设置**根引用**属性还可以提高用户接口性能在此情况下。  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk 编辑器](../core/using-biztalk-editor.md)