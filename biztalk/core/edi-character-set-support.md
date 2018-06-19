---
title: EDI 字符集支持 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4f4492b-8cbe-48ed-810a-3e73e1cb5996
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da903e0cde796c6b12c30ea32dfe4012215a231e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005830"
---
# <a name="edi-character-set-support"></a>EDI 字符集支持
本主题指出的 BizTalk Server EDI 功能中支持的字符集。  
  
|EDI 编码|支持的字符集|  
|------------------|------------------------------|  
|X 12（包括 HIPAA）|X12 -“基本”字符集（ASCII 的子集）|  
|-|X12 -“扩展”字符集（是 ASCII 的子集，同时包含 ISO8859-1 字符）|  
|-|UTF8/UNICODE|  
|EDIFACT|UNOA|  
|-|UNOB|  
|-|UNOC-ISO 8859-1： 信息处理-第 1 部分： 拉丁字母否。 1|  
|-|KECA - KS_C_5601-1987（Windows 949 代码页）|  
|-|UNOX (ISO2022 – JP)|  
|-|UNOY-UTF8 编码的数据**注意：** UNOD 通过 UNOK 字符设置的支持 UTF8 编码的数据也受支持。|  
  
## <a name="setting-the-edi-character-set"></a>设置 EDI 字符集  
 对于 X12 编码的交换，可以通过设置 CharacterSet 管道属性来设置管道的字符集。 有关详细信息，请参阅[配置 EDI 管道属性](../core/configuring-edi-pipeline-properties.md)。  
  
> [!NOTE]
>  在 BizTalk Server 管理控制台的“X12 EDI 属性”对话框的“X12 交换信封生成”页中有一个 X12 字符集控件，但此控件只用于验证为“EDI 属性”对话框中的属性输入的值。  
  
 对于 EDIFACT 编码的交换，可以通过如下方法为参与方设置字符集：在作为交换接收方的参与方的“UNB 段定义”属性页中设置 UNB1.1 参与方属性。 传入交换中使用的编码由交换标头中 UNB1.1 字段的值决定。 有关详细信息，请参阅[配置信封 （EDIFACT 事务设置设置）](../core/configuring-envelopes-edifact-transaction-set-settings.md)。  
  
## <a name="see-also"></a>另请参阅  
 [配置 EDI 管道属性](../core/configuring-edi-pipeline-properties.md)   
 [配置信封（EDIFACT-事务集设置）](../core/configuring-envelopes-edifact-transaction-set-settings.md)