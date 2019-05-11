---
title: BizTalk Server 中的 SWIFT 错误代码 |Microsoft Docs
description: SWIFT 加速器在 BizTalk Server 中查看的类和验证类型
ms.custom: ''
ms.date: 08/16/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03699986-965b-4a28-ab2e-09f110fb4db6
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eeefb9fc918893b8caaab6852d77a417cab340e3
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529791"
---
# <a name="swift-error-codes"></a>SWIFT 错误代码
SWIFT 定义财务 (FIN) 消息的一组的多个网络造成的验证。 每个验证与针对该消息，内容检查的类型相关，并且与三个字符的错误代码相关联。 错误代码的第一个字符表示检测到，此问题的类和是一个字母。 剩余的两个字符表示错误 （如果与此类结合使用） 的详细信息，并且始终显示为两位数字代码。  

## <a name="class-of-errors"></a>类的错误  
 下表列出了字母命名、 验证类型，每个类别的错误，与关联的规则更改，该值指示是否支持错误的类。  
  
|类|验证类型和规则的更改|支持？|  
|-----------|-------------------------------------|----------------|  
|**C，D，E**|语义验证规则 0 299|支持|  
|**Knn**|字段中的无效代码字*nn*|支持|  
|**M50**|已超过消息长度|不支持|  
|**M60**|遇到非 SWIFT 字符|支持|  
|**T**|文本验证错误代码|支持|  
|**G**|消息用户组 （杯褐色） Textval 规则的特定错误代码|不支持|  
|**B**|增值服务的特殊的错误代码|不支持|  
  
 应在中引用所有 SWIFT 错误*SWIFT 用户手册*。 有关详细信息和有关 SWIFT 错误代码的完整列表，请参阅*消息格式的验证规则*量*SWIFT 用户手册*。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 在此发布的 2003 年 9 月版本中实施规则。 您可以访问 SWIFT 网站下载，网址[ http://go.microsoft.com/fwlink/?LinkId=27885 ](http://go.microsoft.com/fwlink/?LinkId=27885)。  

## <a name="validation-errors"></a>验证错误  
 有一些代码由 A4SWIFT 定义的。 创建和实现通过 A4SWIFT，因此没有为此类规则定义 SWIFT 没有相应的错误代码的验证/网络规则中使用这些错误代码。 下表显示了错误代码和相应的用例中引发错误。 是将引发错误的特定字段。  
  
|错误代码|Description|  
|----------------|-----------------|  
|A4SWIFT001|多行的字段的第一个字符不能为: 或-字符的第二个和后续行。|  
|A4SWIFT002|字段包含无效值。|  
  
> [!NOTE]
>  [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] 包含对一些旧的消息的支持，因为内部应用程序可能会使用这些消息。 因此，A4SWIFT 维护关联的 SWIFT 规则和错误代码。

## <a name="more-good-info"></a>更多有用信息
[故障排除：问题和解决方法](troubleshooting-issues-and-resolutions1.md)  
[已知问题](known-issues5.md)  
[通用术语和定义](glossary6.md)