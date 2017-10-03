---
title: "错误-提升的属性 Max Occurs |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.promoPropMaxOccurs
ms.assetid: fc07367e-40f2-46e9-aeeb-bfa2498b1b37
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9c8395757d19eff5241d47c31b15409a00b6faf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---promoted-property-max-occurs"></a>发生错误的最大提升的属性
**错误代码**  
  
 BEC2002  
  
 **说明**  
  
 设置**Max Occurs**属性要升级的节点或其上级节点，之一是与属性提升不兼容。 对于可能会在实例消息中多次出现的节点而言，不能进行属性升级。 因此， **Max Occurs**从回根节点正在升级的节点的所有节点的属性必须设置为 1。  
  
 **用户执行任何操作**  
  
 确保**Max Occurs**要升级的节点和所有其祖先节点的属性设置为一 (1)。