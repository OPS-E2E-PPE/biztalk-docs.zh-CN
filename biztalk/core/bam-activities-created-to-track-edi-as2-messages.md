---
title: 为跟踪 edi/as2 消息创建 BAM 活动 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a10ab846-0fbb-46f5-920e-cb2b5be75814
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a3760513c79cb6fc006c29276b73b8b475e64ea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358995"
---
# <a name="bam-activities-created-to-track-edi-as2-messages"></a>为跟踪 edi/as2 消息创建的 BAM 活动
BizTalk Server 包含已为 EDI 和 AS2 状态报告创建的 BAM 活动。 这些活动可确定在状态报告中显示的数据。 本主题描述 BAM 活动和中，定义的字段，并说明了为 BAM 活动中的某些字段定义的枚举值。  
  
 可以通过创建自定义 BAM 活动来创建自定义状态报告。 自定义活动可以基于标准的活动之一。 此外可以通过查询 BizTalkDTADb 数据库中的 EdiMessageContent 表显示来自自定义状态报告的消息的内容。 有关详细信息，请参阅下面的"查询 EdiMessageContent 表"部分。  
  
> [!CAUTION]
>  修改 BAM 活动可能会影响 BizTalk EDI 和 AS2 运行时，这取决于活动的处理。  
  
## <a name="bam-activities-used-in-status-reporting"></a>状态报告中使用的 BAM 活动  
 包含作为 BAMPrimaryImport 数据库中的视图创建为跟踪 EDI/AS2 消息的 BAM 活动。 下表列出了 BAM 活动和其中的列：  
  
|BAM 活动|字段|  
|------------------|------------|  
|AS2InterchangeActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> Direction<br /><br /> MessageID<br /><br /> AS2From<br /><br /> AS2To<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> LastModified|  
|AS2MdnActivity|RecordID<br /><br /> ActivityID<br /><br /> AS2PartyRole<br /><br /> AS2From<br /><br /> AS2To<br /><br /> MessageID<br /><br /> MdnDateTime<br /><br /> MdnDispositionType<br /><br /> DispositionModifierExtType<br /><br /> DispositionModifierExtDescription<br /><br /> MdnEncryptionType<br /><br /> MdnSignatureType<br /><br /> MdnPayloadContentKey<br /><br /> MdnWireContentKey<br /><br /> MdnMicValue<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> LastModified|  
|AS2MessageActivity|RecordID<br /><br /> ActivityID<br /><br /> ReceiverPartyName<br /><br /> SenderPartyName<br /><br /> AS2PartyRole<br /><br /> AS2From<br /><br /> AS2To<br /><br /> MessageID<br /><br /> MessageDateTime<br /><br /> BTSInterchangeID<br /><br /> BTSMessageID<br /><br /> MdnProcessingStatus<br /><br /> MessageEncryptionType<br /><br /> IsMdnExpected<br /><br /> MicAlgorithmType<br /><br /> MessageSignatureType<br /><br /> MessagePayloadContentKey<br /><br /> MessageWireContentKey<br /><br /> MessageMicValue<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> IsAS2MessageDuplicate<br /><br /> DaysToCheckDuplicate<br /><br /> FileName<br /><br /> TrackingActivityID<br /><br /> LastModified|  
|BatchingActivity|RecordID<br /><br /> ActivityID<br /><br /> BatchStatus<br /><br /> DestinationPartyID<br /><br /> DestinationPartyName<br /><br /> ActivationTime<br /><br /> BatchOccurrenceCount<br /><br /> EdiEncodingType<br /><br /> BatchType<br /><br /> TargetedBatchCount<br /><br /> ScheduledReleaseTime<br /><br /> BatchElementCount<br /><br /> RejectedBatchElementCount<br /><br /> BatchSize<br /><br /> LastBatchAction<br /><br /> CreationTime<br /><br /> ReleaseTime<br /><br /> BatchReleaseType<br /><br /> BatchServiceID<br /><br /> ActivationMessageID<br /><br /> ReleaseMessageID<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> BatchCorrelationID<br /><br /> BatchName<br /><br /> BatchID<br /><br /> LastModified|  
|BatchInterchangeActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverPartyName<br /><br /> SenderPartyName<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> Direction<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> BatchCorrelationID<br /><br /> LastModified|  
|BusinessMessageJournal|RecordID<br /><br /> ActivityID<br /><br /> MessageTrackingID<br /><br /> ActionType<br /><br /> ContainerActivityID<br /><br /> ContainerType<br /><br /> BTSInterchangeID<br /><br /> BTSMessageId<br /><br /> BTSServiceInstanceId<br /><br /> BTSHostName<br /><br /> RoutedToPartyName<br /><br /> LinkedMessageTrackingID<br /><br /> TimeCreated<br /><br /> LastModified|  
|FunctionalAckActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeActivityID<br /><br /> GroupControlNo<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> Direction<br /><br /> AckProcessingStatus<br /><br /> AckStatusCode<br /><br /> DeliveredTSCount<br /><br /> AcceptedTSCount<br /><br /> AckIcn<br /><br /> AckIcnDate<br /><br /> AckIcnTime<br /><br /> ErrorCode1<br /><br /> ErrorCode2<br /><br /> ErrorCode3<br /><br /> ErrorCode4<br /><br /> ErrorCode5<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> LastModified|  
|FunctionalGroupInfo|RecordID<br /><br /> ActivityID<br /><br /> InterchangeActivityID<br /><br /> GroupControlNo<br /><br /> FunctionalIDCode<br /><br /> TSCount<br /><br /> LastModified|  
|InterchangeAckActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> Direction<br /><br /> AckProcessingStatus<br /><br /> AckStatusCode<br /><br /> AckIcn<br /><br /> AckIcnDate<br /><br /> AckIcnTime<br /><br /> AckNoteCode1<br /><br /> AckNoteCode2<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> AckCorrelationId<br /><br /> LastModified|  
|InterchangeStatusActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> ReceiverPartyName<br /><br /> SenderPartyName<br /><br /> InterchangeDateTime<br /><br /> Direction<br /><br /> AckStatusCode<br /><br /> GroupCount<br /><br /> EdiMessageType<br /><br /> PortID<br /><br /> IsInterchangeAckExpected<br /><br /> IsFunctionalAckExpected<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> AckCorrelationId<br /><br /> TsCorrelationId<br /><br /> LastModified|  
|ResendJournalActivity|RecordID<br /><br /> ActivityID<br /><br /> TrackingActivityId<br /><br /> ResendIndex<br /><br /> ResendStatus<br /><br /> BTSInterchangeID<br /><br /> LastModified|  
|ResendTrackingActivity|RecordID<br /><br /> ActivityID<br /><br /> CorrelationId<br /><br /> AdapterPrefix<br /><br /> ResendCount<br /><br /> MaxResendCount<br /><br /> ResendInterval<br /><br /> MaxRetryCount<br /><br /> RetryInterval<br /><br /> MessageContentID<br /><br /> ResendTimeout<br /><br /> RetryTimeout<br /><br /> BTSInterchangeID<br /><br /> LastModified|  
|TransactionSetActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> Direction<br /><br /> ReceiverPartyName<br /><br /> SenderPartyName<br /><br /> ApplicationSender<br /><br /> ApplicationReceiver<br /><br /> GroupDateTime<br /><br /> GroupControlNo<br /><br /> TransactionSetId<br /><br /> DocType<br /><br /> TransactionSetControlNo<br /><br /> AckStatusCode<br /><br /> BatchProcessing<br /><br /> ProcessingDateTime<br /><br /> GroupOrdinal<br /><br /> TransactionSetOrdinal<br /><br /> MessageContentKey<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> TsCorrelationId<br /><br /> LastModified|  
  
## <a name="data-enumerations-in-the-bamprimaryimport-database"></a>BAMPrimaryImport 数据库中的数据枚举  
 某些 EDI 和 AS2 数据另存为 BAMPrimaryImport 数据库的表中的枚举。 当显示在状态报告中，数据显示为文本。 其值如下所示：  
  
|字段|枚举值|  
|-----------|-----------------|  
|AckProcessingStatus|NotExpected = -1<br /><br /> 预期 = 0<br /><br /> 收到 = 1<br /><br /> 发送 = 2<br /><br /> 生成 = 3|  
|AS2PartyRole|所有 = 0<br /><br /> 接收方 = 1<br /><br /> 发件人 = 2|  
|BatchAction|创建 = 0<br /><br /> 激活 = 1<br /><br /> ElementReference = 2<br /><br /> 发布 = 3<br /><br /> 重写 = 4<br /><br /> 终止 = 5<br /><br /> 发送 = 6<br /><br /> ToBeReleased = 7|  
|BatchStatus|所有 =-1<br /><br /> 定义 = 0<br /><br /> 在职<br /><br /> Released<br /><br /> 已完成|  
|BatchType|ScheduleBased = 0<br /><br /> MessagesCountInGroup = 1<br /><br /> MessagesCountIn<br />交换 = 2<br /><br /> CharacterCount = 3<br /><br /> ExternalTrigger = 4|  
|Direction|所有 = 0<br /><br /> 接收 = 1<br /><br /> 发送 = 2|  
|DisplayAckStatusCode|所有 = 100<br /><br /> 已接受 = 0<br /><br /> PartiallyAccepted = 1<br /><br /> 已拒绝 =-1<br /><br /> AckExpected = 500<br /><br /> AckNotExpected = 600|  
|DispositionModifierExt<br />Description|非值 = 1<br /><br /> 身份验证失败 = 2<br /><br /> 解密失败 = 3<br /><br /> 没有足够的消息<br />安全 = 4<br /><br /> 完整性检查失败 = 5<br /><br /> 出现意外的处理 <br />错误 = 6|  
|DispositionModifierExt<br />类型|非值 = 1<br /><br /> 错误 = 2<br /><br /> 警告 = 3|  
|EdiMessageType|X12，<br /><br /> Edifact，<br /><br /> Unknown|  
|IsMdnExpected|非预期的 MDN = 0<br /><br /> MDN 符合预期 = 1|  
|MdnDispositionType|处理 = 1<br /><br /> 失败 = 2|  
|MdnProcessingStatus|所有 = 0<br /><br /> 处理 = 1<br /><br /> 失败 = 2<br /><br /> 预期 = 3<br /><br /> 不应 = 4|  
|MessageEncryptionType|消息未加密 = 0<br /><br /> 加密消息 = 1|  
|MessageSignatureType|未签名消息 = 0<br /><br /> 消息签名 = 1|  
|MicAlgorithmType|未知的类型 =-1<br /><br /> SHA1 = 1<br /><br /> MD5 = 2|  
  
## <a name="businessmessagejournal-bam-activity"></a>BusinessMessageJournal BAM 活动  
 BusinessMessageJournal BAM 活动，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要将包含事务集与包含在同一个事务的传出批交换将接收的 EDI 交换的关联设置。 有关详细信息，请参阅[关联与传出批的传入事务集](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md)。  
  
##  <a name="BKMK_Query"></a> 查询 EdiMessageContent 表  
 BizTalkDTADb 数据库中的 EdiMessageContent 表存储消息负载，以及消息元数据。 通过自定义状态报告，您可以查询 EdiMessageContent 表以显示消息内容。 这是类似于某些状态报告在产品如何使您能够显示消息内容，例如，如何的 AS2 消息和相关 MDN 状态报告可显示消息线路格式。  
  
 自定义 BAM 活动中与 EdiMessageContent 表使用链接到 EdiMessageContent 表中的 ContentKey 列对应的键列将 BAM 活动中。 例如，若要从 AS2MessageActivity BAM 活动链接到 EdiMessageContent 表，您将使用 MessagePayloadContentKey 列或 MessageWireContentKey 列链接到 ContentKey 列。  
  
|表|“列”|  
|-----------|-------------|  
|EdiMessageContent<br /><br /> （在 BizTalkDTADb 数据库中）|ContentKey<br /><br /> MessageFormat<br /><br /> ContentType<br /><br /> 字符集<br /><br /> TimeCreated<br /><br /> TimeInserted<br /><br /> IsOrphaned<br /><br /> ContentBinary|  
  
## <a name="see-also"></a>请参阅  
 [如何为 EDI 和 AS2 状态报告存储数据](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)   
 [将传入事务集与传出批相关联](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md)