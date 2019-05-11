---
title: 错误-已升级的属性 Max Occurs |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.promoPropMaxOccurs
ms.assetid: fc07367e-40f2-46e9-aeeb-bfa2498b1b37
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fcaf06dc0fccbf838c401343b3ce1e8f3b538ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347049"
---
# <a name="error---promoted-property-max-occurs"></a>错误-已升级的属性 Max Occurs
**错误代码**  
  
 BEC2002  
  
 **说明**  
  
 设置**Max Occurs**或某个祖先节点，要升级的节点的属性是与属性升级不兼容。 可以在实例消息中多次出现的节点不允许使用属性升级。 因此， **Max Occurs**从要升级到的根节点的节点的所有节点的属性必须设置为 1。  
  
 **用户执行任何操作**  
  
 絋粄**Max Occurs**要升级的节点及其所有祖先节点的属性设置为一 (1)。