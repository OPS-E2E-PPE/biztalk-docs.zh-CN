---
title: "BizTalk Server 中的 SWIFT 错误代码 |Microsoft 文档"
description: "SWIFT 快捷键 BizTalk Server 中查看的类和验证类型"
ms.custom: 
ms.date: 08/16/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03699986-965b-4a28-ab2e-09f110fb4db6
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6d8e027eb9cce1cf66342484070310141e10b5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="swift-error-codes"></a>SWIFT 错误代码
SWIFT 定义许多网络施加验证针对的一组财务 (FIN) 消息。 每个验证与一种针对消息，内容检查，并且与三个字符错误代码相关联。 错误代码的第一个字符表示检测到，此问题的类和是一个字母。 剩余的两个字符表示的错误 （与类结合使用） 时的详细信息，并始终显示为两位数字代码。  

## <a name="class-of-errors"></a>类的错误  
 下表列出了字母命名、 验证类型，每个类别的错误，与关联的规则更改，是否受支持的错误的类。  
  
|类|验证类型和规则更改|是否支持？|  
|-----------|-------------------------------------|----------------|  
|**C，D，E**|语义验证规则 0 299|是否支持|  
|**Knn**|字段中的无效代码字*nn*|是否支持|  
|**M50**|已超过消息长度|不支持|  
|**M60**|遇到的非 SWIFT 字符|是否支持|  
|**T**|文本验证错误代码|是否支持|  
|**G**|消息用户组 （咖啡杯） Textval 规则的特定错误代码|不支持|  
|**B**|增值服务的特殊的错误代码|不支持|  
  
 应在中引用所有 SWIFT 错误*SWIFT 用户手册*。 有关详细信息和有关 SWIFT 错误代码的完整列表，请参阅*消息格式验证规则*量*SWIFT 用户手册*。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]在此发布的 2003 年 9 月版本中实施规则。 你可以访问位于的 SWIFT 网站[http://go.microsoft.com/fwlink/?LinkId=27885](http://go.microsoft.com/fwlink/?LinkId=27885)。  

## <a name="validation-errors"></a>验证错误  
 有一些代码 A4SWIFT 定义。 创建和实现通过 A4SWIFT，因此没有为此类规则定义 SWIFT 相应错误代码的验证/网络规则用于这些错误代码。 下表显示的错误代码和相应的情况下引发错误的。 是将引发错误的特定字段。  
  
|错误代码|Description|  
|----------------|-----------------|  
|A4SWIFT001|多行的字段的第一个字符不能为: 或-字符的第二个和后续行。|  
|A4SWIFT002|字段包含无效值。|  
  
> [!NOTE]
>  [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]因为内部应用程序可能会使用这些消息，请包括对某些旧的消息，支持。 因此，A4SWIFT 维护关联的 SWIFT 规则和错误代码。

## <a name="more-good-info"></a>良好的详细信息
[疑难解答： 问题和解决方法](troubleshooting-issues-and-resolutions1.md)  
[已知问题](known-issues5.md)  
[常见术语和定义](glossary6.md)