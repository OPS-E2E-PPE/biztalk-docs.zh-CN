---
title: EDI 数据元素结构元素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 775e8b87-b952-46d2-a506-5174d216a9aa
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b36433f3cf4cf4a8f14ac70467d870a727db7dd9
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530832"
---
# <a name="edi-data-element-structural-element"></a>EDI 数据元素结构元素
数据元素是消息中数据的主计价单位。 数据元素由数据元素分隔符，这是默认情况下，对于 X12 是星号，默认情况下，对于 EDIFACT 是加号分隔。 数据元素的可行性定义为必需、 可选或条件。  
  
 数据元素可以是简单或复合。 简单数据元素为数值型，它们的数据的最低级别。 复合数据元素是一串子元素，这是由复合元素分隔符分隔的简单数据元素。 默认情况下，组件分隔符是 X12 和 EDIFACT 的冒号。  
  
 对于 EDIFACT 编码的消息，如果经由 EDI 发送的数据需要发送任何定义用作分隔符的字符需要使用转义符来指明后面的字符不是一个分隔符，而是数据的一部分。 转义符为问号 （？） 默认情况下。  
  
> [!NOTE]
>  对于 X12 不支持转义符。 如果遇到作为 X12 编码的交换，在接收或发送端的数据的一部分分隔符将挂起交换。