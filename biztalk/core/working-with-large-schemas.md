---
title: 处理大型架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8348036d-6edb-46a3-badd-0223cfe0a92f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f122d56c5a5632a3d6edcb785968c51f487f0b8b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295371"
---
# <a name="working-with-large-schemas"></a>处理大型架构
当架构变得非常大时，可能会发现刷新 XSD 视图变得越来越慢，也可以受到影响的用户界面其他方面的响应。 此问题的解决方案是关闭自动刷新功能，并改为使用手动**刷新**XSD 视图来定期刷新 XSD 视图中的链接。 有关分步说明有关如何启用自动刷新功能关闭，请参阅"打开和关闭自动刷新 XSD 视图的"过程中[管理 XSD 视图](../core/how-to-manage-the-xsd-view.md)。  
  
 性能也可能较慢大型架构中有多个附加到的根**架构**节点。 设置**根引用**属性可能会增加用户界面中的性能。 设置**根引用**提高性能，因为编译器会创建C#类为所有根架构。 单个节点意味着创建较少的类。  
  
 **验证实例**可能会出现在用户界面中缓慢，因为始终执行验证的架构验证实例之前。 仅在用户界面中进行架构验证。 设置**根引用**属性还提高了用户界面的性能在这种情况下。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk 编辑器](../core/using-biztalk-editor.md)