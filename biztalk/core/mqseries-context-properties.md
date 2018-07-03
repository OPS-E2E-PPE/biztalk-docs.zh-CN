---
title: MQSeries 上下文属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQXQH_RemoteQName property [MQSeries adapters]
- MQCIH_TaskEndStatus property [MQSeries adapters]
- MQIIH_SecurityScope property [MQSeries adapters]
- MQCIH_AbendCode property [MQSeries adapters]
- filters, MQSeries adapters
- MQCIH_ReturnCode property [MQSeries adapters]
- MQCIH_TransactionId property [MQSeries adapters]
- MQCIH_ReplyToFormat property [MQSeries adapters]
- MQMD_ReplyToQ property [MQSeries adapters]
- MQMD_PutTime property [MQSeries adapters]
- configuring [MQSeries adapters], properties
- MQMD_PutApplName property [MQSeries adapters]
- configuring [MQSeries adapters], filtering
- MQCIH_UOWControl property [MQSeries adapters]
- MQCIH_ErrorOffset property [MQSeries adapters]
- MQMD_Priority property [MQSeries adapters]
- MQMD_MsgSeqNumber property [MQSeries adapters]
- MQMD_Format property [MQSeries adapters]
- MQCIH_ConversationalTask property [MQSeries adapters]
- Message Descriptor table [MQSeries adapters]
- MQMD_Feedback property [MQSeries adapters]
- MQCIH_Authenticator property [MQSeries adapters]
- MQIIH_TranState property [MQSeries adapters]
- MQCIH_AttentionId property [MQSeries adapters]
- MQMD_UserIdentifier property [MQSeries adapters]
- MQCIH_Flags property [MQSeries adapters]
- MQMD_CorrelId property [MQSeries adapters]
- MQIIH_Format property [MQSeries adapters]
- MQMD_Offset property [MQSeries adapters]
- MQMD_BackoutCount property [MQSeries adapters]
- MQMD_Report property [MQSeries adapters]
- MQMD_MsgFlags property [MQSeries adapters]
- MQSeries adapters, filtering
- MQMD_ApplIdentityData property [MQSeries adapters]
- MQIIH_Authenticator property [MQSeries adapters]
- MQIIH_MFSMapName property [MQSeries adapters]
- MQCIH_LinkType property [MQSeries adapters]
- MQMD_Persistence property [MQSeries adapters]
- MQCIH_CursorPosition property [MQSeries adapters]
- MQCIH_Format property [MQSeries adapters]
- MQCIH_Facility property [MQSeries adapters]
- MQCIH_CancelCode property [MQSeries adapters]
- MQMD_PutDate property [MQSeries adapters]
- MQCIH_NextTransactionId property [MQSeries adapters]
- MQIIH_CommitMode property [MQSeries adapters]
- MQIIH_ReplyToFormat property [MQSeries adapters]
- MQCIH_Function property [MQSeries adapters]
- MQMD_ReplyToQMgr property [MQSeries adapters]
- MQCIH_StartCode property [MQSeries adapters]
- MQMD_Expiry property [MQSeries adapters]
- MQMD_PutApplType property [MQSeries adapters]
- MQCIH_FacilityLike property [MQSeries adapters]
- MQIIH_Flags property [MQSeries adapters]
- MQCIH_CompCode property [MQSeries adapters]
- MQSeries adapters, properties
- MQCIH_FacilityKeepTime property [MQSeries adapters]
- MQMD_ApplOriginData property [MQSeries adapters]
- MQCIH_Reason property [MQSeries adapters]
- MQIIH_LTermOverride property [MQSeries adapters]
- MQMD_CodedCharSetId property [MQSeries adapters]
- MQMD_GroupID property [MQSeries adapters]
- MQXQH_RemoteQMgrName property [MQSeries adapters]
- MQMD_MsgType property [MQSeries adapters]
- MQMD_OriginalLength property [MQSeries adapters]
- MQMD_Encoding property [MQSeries adapters]
- MQMD_AccountingToken property [MQSeries adapters]
- MQCIH_OutputDataLength property [MQSeries adapters]
- MQIIH_TranInstanceId property [MQSeries adapters]
- MQCIH_GetWaitInterval property [MQSeries adapters]
- MQCIH_ADSDescriptor property [MQSeries adapters]
- MQMD_MsgId property [MQSeries adapters]
ms.assetid: 1b22b7d7-432b-4ec5-938c-c43077ce3e0f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 684fad8e1a417e9faf7127a81a4e8f7d6f10e630
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976590"
---
# <a name="mqseries-context-properties"></a>MQSeries 上下文属性
MQSeries 适配器提供了一组特定于 MQSeries 的上下文属性以供您在应用程序中使用。 您可以在筛选表达式和业务流程中使用这些属性。  
  
 对于以绑定到 MQSeries 适配器的发送端口为目标的消息，若要将 MQSeries 上下文属性分配给此类消息，请使用消息赋值运算符，并在 MQSeries 命名空间中指定可用的上下文属性之一。  
  
 下面是设置 MQSeries 的示例**MQMD_UserIdentifier**属性：  
  
```  
Message_2(MQSeries.MQMD_UserIdentifier) = "MeMyselfAndI";  
```  
  
 必须从 IBM MQSeries SDK 所附带的 C 编程语言头文件中获得枚举值。 在 Program Files\IBM\WebSphere MQ\Tools\c\include 文件夹中可找到这些文件。 这些文件定义了在设置或读取 MQSeries 上下文属性值时要使用的值。  
  
 十六进制字符串值是表示二进制值的字符串。 这些值不具有诸如 0x 之类的前缀。 它们包含从 0 到 9 的数字，以及从“a”到“f”或“A”到“F”的字母。 适配器将忽略它们之间的空格。  
  
 有关这些属性的详细信息，请参阅 IBM WebSphere MQ 文档。  
  
 下表显示了可用的消息描述符（MQMD 结构）属性的完整集以及其对应的类型和值：  
  
|“属性”|类型|长度|ReplTest1|  
|----------|----------|------------|-----------|  
|**MQMD_AccountingToken**|string|64|十六进制字符串|  
|**MQMD_ApplIdentityData**|string|32|十六进制字符串|  
|**MQMD_ApplOriginData**|string|4|String<br /><br /> **默认值：** 空间|  
|**MQMD_BackoutCount**|unsigned int|4|Number<br /><br /> 只读<br /><br /> **默认值：** 0|  
|**MQMD_CodedCharSetId**|unsigned int|4|Number<br /><br /> **默认值：** 0|  
|**MQMD_CorrelId**|string|48|十六进制字符串|  
|**MQMD_Encoding**|unsigned int|4|Number<br /><br /> 使用头文件值。 **默认值：** 0|  
|**MQMD_Expiry**|unsigned int|4|Number|  
|**MQMD_Feedback**|unsigned int|4|Number<br /><br /> 使用头文件值。 **默认值：** 0|  
|**MQMD_Format**|string|8|String<br /><br /> 如果此属性设置为 MQXMIT，则应确保 MQXQH 属性具有相应值。|  
|**MQMD_GroupID**|string|48|十六进制字符串|  
|**MQMD_MsgFlags**|unsigned int|4|Number<br /><br /> 使用头文件值。 **默认值：** 0|  
|**MQMD_MsgId**|string|48|十六进制字符串|  
|**MQMD_MsgSeqNumber**|unsigned int|4||  
|**MQMD_MsgType**|unsigned int|4|Number<br /><br /> 使用头文件值。|  
|**MQMD_Offset**|unsigned int|4||  
|**MQMD_OriginalLength**|unsigned int|4||  
|**MQMD_Persistence**|unsigned int|4|Number<br /><br /> 使用头文件值。|  
|**MQMD_Priority**|unsigned int|4|Number|  
|**MQMD_PutApplName**|string|28|String<br /><br /> **默认值：** 空间|  
|**MQMD_PutApplType**|unsigned int|4|Number<br /><br /> 使用头文件值。 **默认值：** 0|  
|**MQMD_PutDate**|string|8|date|  
|**MQMD_PutTime**|string|8|Time|  
|**MQMD_ReplyToQ**|string|48|String<br /><br /> **默认值：** 空间|  
|**MQMD_ReplyToQMgr**|string|48|String<br /><br /> **默认值：** 空间|  
|**MQMD_Report**|unsigned int|4|Number<br /><br /> 使用头文件值。|  
|**MQMD_UserIdentifier**|string|12|String<br /><br /> 当你使用时，包含用户标识符**SSOAffiliateApplication**属性。|  
  
 在直接从 MQSeries 传输队列中接收消息时，MQSeries 适配器将设置该传输队列标头属性（MQXQH 数据结构）的格式，并将其放置在其对应的上下文属性中。 当直接向 MQSeries 传输队列发送消息，标头属性被格式化，并从相应的上下文属性仅当分配值**MQMD_Format**属性具有值为 mqxmit 时。 下表介绍的属性。  
  
|“属性”|类型|长度|ReplTest1|  
|----------|----------|------------|-----------|  
|**MQXQH_RemoteQMgrName**|string|48|string|  
|**MQXQH_RemoteQName**|string|48|string|  
  
 与本主题前面部分列出的属性一样，该适配器将按照相同的规则填充以下消息描述符值。 该适配器使用 MQXQH_ 而不是 MQMD_ 作为这些属性名的前缀，否则这些属性将直接映射到在消息描述符表中定义的那些属性：  
  
- **MQXQH_MsgDesc_AccountingToken**  
  
- **MQXQH_MsgDesc_ApplIdentityData**  
  
- **MQXQH_MsgDesc_ApplOriginData**  
  
- **MQXQH_MsgDesc_BackoutCount**  
  
- **MQXQH_MsgDesc_CodedCharSetId**  
  
- **MQXQH_MsgDesc_CorrelId**  
  
- **MQXQH_MsgDesc_Encoding**  
  
- **MQXQH_MsgDesc_Expiry**  
  
- **MQXQH_MsgDesc_Feedback**  
  
- **MQXQH_MsgDesc_Format**  
  
- **MQXQH_MsgDesc_MsgId**  
  
- **MQXQH_MsgDesc_MsgType**  
  
- **MQXQH_MsgDesc_Persistence**  
  
- **MQXQH_MsgDesc_Priority**  
  
- **MQXQH_MsgDesc_PutApplName**  
  
- **MQXQH_MsgDesc_PutApplType**  
  
- **MQXQH_MsgDesc_PutDate**  
  
- **MQXQH_MsgDesc_PutTime**  
  
- **MQXQH_MsgDesc_ReplyToQ**  
  
- **MQXQH_MsgDesc_ReplyToQMgr**  
  
- **MQXQH_MsgDesc_Report**  
  
- **MQXQH_MsgDesc_UserIdentifier**  
  
  属性架构中还包含与 MQSeries 相关的其他属性，这些属性可在筛选表达式中使用。 下表列出了这些属性：  
  
|“属性”|类型|长度|ReplTest1|  
|----------|----------|------------|-----------|  
|**MQCIH_AbendCode**|string|4||  
|**MQCIH_ADSDescriptor**|unsigned int|4||  
|**MQCIH_AttentionId**|string|4||  
|**MQCIH_Authenticator**|string|8|当你使用设置为 SSO 密码**SSOAffiliateApplication**属性。 **注意：** 此值将设置为空的 MQSeries 适配器，如果 SSO 密码的长度超过 8 个字符。|  
|**MQCIH_CancelCode**|string|4||  
|**MQCIH_CompCode**|unsigned int|4||  
|**MQCIH_ConversationalTask**|unsigned int|4||  
|**MQCIH_CursorPosition**|unsigned int|4||  
|**MQCIH_ErrorOffset**|unsigned int|4||  
|**MQCIH_Facility**|string|16|十六进制字符串|  
|**MQCIH_FacilityKeepTime**|unsigned int|4||  
|**MQCIH_FacilityLike**|string|4||  
|**MQCIH_Flags**|unsigned int|4||  
|**MQCIH_Format**|string|||  
|**MQCIH_Function**|string|4||  
|**MQCIH_GetWaitInterval**|unsigned int|4||  
|**MQCIH_LinkType**|unsigned int|4||  
|**MQCIH_NextTransactionId**|string|4||  
|**MQCIH_OutputDataLength**|unsigned int|4||  
|**MQCIH_Reason**|unsigned int|4||  
|**MQCIH_ReplyToFormat**|string|||  
|**MQCIH_ReturnCode**|unsigned int|4||  
|**MQCIH_StartCode**|string|4||  
|**MQCIH_TaskEndStatus**|unsigned int|4||  
|**MQCIH_TransactionId**|string|4||  
|**MQCIH_UOWControl**|unsigned int|4||  
|**MQIIH_Authenticator**|string|8|当你使用设置为 SSO 密码**SSOAffiliateApplication**属性。 **注意：** 此值将设置为空的 MQSeries 适配器，如果 SSO 密码的长度超过 8 个字符。|  
|**MQIIH_CommitMode**|string|||  
|**MQIIH_Flags**|unsigned int|4||  
|**MQIIH_Format**|string|||  
|**MQIIH_LTermOverride**|string|8||  
|**MQIIH_MFSMapName**|string|8||  
|**MQIIH_ReplyToFormat**|string|||  
|**MQIIH_SecurityScope**|string|||  
|**MQIIH_TranInstanceId**|string|32|十六进制字符串|  
|**MQIIH_TranState**|string|||  
  
## <a name="see-also"></a>请参阅  
 [MQSeries 适配器属性](../core/mqseries-adapter-properties.md)   
 [与 BizTalk Server 相关的属性](../core/properties-related-to-biztalk-server.md)   
 [属性的数据类型转换](../core/data-type-conversion-of-properties.md)