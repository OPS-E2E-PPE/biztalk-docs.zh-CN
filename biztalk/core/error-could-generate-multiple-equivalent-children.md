---
title: "错误-无法生成多个等效的子节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.couldGenMultipleEquivChildren
ms.assetid: ef3ea6db-6759-4f38-804c-e32a1f24d758
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 686899c2871ded25f6901e919e9283694b9bacf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---could-generate-multiple-equivalent-children"></a>错误-无法生成多个等效的子节点
**错误代码**  
  
 btm1026  
  
 **说明**  
  
 指向目标架构不正确，导致多个节点对**等效**组节点以便生成。  
  
 **用户执行任何操作**  
  
 重新链接到目标架构，可能使用逻辑 functoid，因此，只有单个节点内的**等效**可以在映射过程中生成组节点。