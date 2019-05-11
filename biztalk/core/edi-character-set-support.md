---
title: EDI 字符集支持 |Microsoft Docs
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
ms.openlocfilehash: 5c38e7a8115be79d44e39cb4b1c60ef975219ad7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350459"
---
# <a name="edi-character-set-support"></a>EDI 字符集支持
本主题指明 BizTalk Server EDI 功能中支持哪些字符集。  
  
|EDI 编码|支持的字符集|  
|------------------|------------------------------|  
|X12 （包括 HIPAA）|X12-基本字符集 （ASCII 的子集）|  
|-|X12 扩展字符集 (ASCII 的子集，还包括 ISO8859-1 个字符)|  
|-|UTF8/UNICODE|  
|EDIFACT|UNOA|  
|-|UNOB|  
|-|UNOC-ISO 8859-1:信息处理-第 1 部分：拉丁字母表不能。 1|  
|-|KECA-KS_C_5601-1987年 （Windows 949 代码页）|  
|-|UNOX (ISO2022-JP)|  
|-|UNOY-UTF8 编码数据**注意：** UNOD 到 UNOK 字符设置的支持 UTF8 编码的数据也受支持。|  
  
## <a name="setting-the-edi-character-set"></a>设置 EDI 字符集  
 对于 X12 编码的交换，可以设置为管道通过设置 CharacterSet 管道属性设置的字符。 有关详细信息，请参阅[配置 EDI 管道属性](../core/configuring-edi-pipeline-properties.md)。  
  
> [!NOTE]
>  没有一个 X12 字符集控件在 X12 中的 EDI 属性对话框框中 BizTalk Server 管理控制台中，但此控件只用于验证的值的 X12 交换信封生成页输入中 EDI 的属性属性对话框。  
  
 对于 EDIFACT 编码的交换，可以设置的字符集的参与方作为交换接收方的参与方的 UNB 段定义属性页中设置 UNB1.1 参与方属性。 将传入交换中使用的编码由交换标头中 UNB1.1 字段的值确定。 有关详细信息，请参阅[配置信封 （EDIFACT-事务集设置）](../core/configuring-envelopes-edifact-transaction-set-settings.md)。  
  
## <a name="see-also"></a>请参阅  
 [配置 EDI 管道属性](../core/configuring-edi-pipeline-properties.md)   
 [配置信封（EDIFACT-事务集设置）](../core/configuring-envelopes-edifact-transaction-set-settings.md)