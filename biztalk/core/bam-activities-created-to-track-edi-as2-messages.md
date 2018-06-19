---
title: BAM 活动创建到跟踪 EDI AS2 消息 |Microsoft 文档
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
ms.openlocfilehash: c7da7ac08a8f26e21b2c648670730db136392471
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008894"
---
# <a name="bam-activities-created-to-track-edi-as2-messages"></a>BAM 活动跟踪 EDI AS2 消息的创建
BizTalk Server 包括 BAM 活动已创建用于 EDI 和 AS2 报告的状态。 这些活动可确定在状态报告中显示的数据。 本主题介绍了其中定义的 BAM 活动和字段，以及为 BAM 活动中的某些字段定义的枚举值。  
  
 您可以通过创建自定义 BAM 活动来创建自定义状态报告。 自定义活动可以基于某一种标准活动。 还可以通过查询 BizTalkDTADb 数据库中的 EdiMessageContent 表，来显示自定义状态报告中的消息内容。 有关详细信息，请参阅下面的“查询 EdiMessageContent 表”部分。  
  
> [!CAUTION]
>  修改 BAM 活动可能会影响 BizTalk EDI 和 AS2 运行时的处理，这两个运行时均依赖于 BAM 活动。  
  
## <a name="bam-activities-used-in-status-reporting"></a>状态报告中使用的 BAM 活动  
 为跟踪 EDI/AS2 消息而创建的 BAM 活动作为视图包含在 BAMPrimaryImport 数据库中。 下表列出了 BAM 活动及其中的列：  
  
|BAM 活动|字段|  
|------------------|------------|  
|AS2InterchangeActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> 方向<br /><br /> MessageID<br /><br /> AS2From<br /><br /> AS2To<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> LastModified|  
|AS2MdnActivity|RecordID<br /><br /> ActivityID<br /><br /> AS2PartyRole<br /><br /> AS2From<br /><br /> AS2To<br /><br /> MessageID<br /><br /> MdnDateTime<br /><br /> MdnDispositionType<br /><br /> DispositionModifierExtType<br /><br /> DispositionModifierExtDescription<br /><br /> MdnEncryptionType<br /><br /> MdnSignatureType<br /><br /> MdnPayloadContentKey<br /><br /> MdnWireContentKey<br /><br /> MdnMicValue<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> LastModified|  
|AS2MessageActivity|RecordID<br /><br /> ActivityID<br /><br /> ReceiverPartyName<br /><br /> SenderPartyName<br /><br /> AS2PartyRole<br /><br /> AS2From<br /><br /> AS2To<br /><br /> MessageID<br /><br /> MessageDateTime<br /><br /> BTSInterchangeID<br /><br /> BTSMessageID<br /><br /> MdnProcessingStatus<br /><br /> MessageEncryptionType<br /><br /> IsMdnExpected<br /><br /> MicAlgorithmType<br /><br /> MessageSignatureType<br /><br /> MessagePayloadContentKey<br /><br /> MessageWireContentKey<br /><br /> MessageMicValue<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> IsAS2MessageDuplicate<br /><br /> DaysToCheckDuplicate<br /><br /> FileName<br /><br /> TrackingActivityID<br /><br /> LastModified|  
|BatchingActivity|RecordID<br /><br /> ActivityID<br /><br /> BatchStatus<br /><br /> DestinationPartyID<br /><br /> DestinationPartyName<br /><br /> ActivationTime<br /><br /> BatchOccurrenceCount<br /><br /> EdiEncodingType<br /><br /> BatchType<br /><br /> TargetedBatchCount<br /><br /> ScheduledReleaseTime<br /><br /> BatchElementCount<br /><br /> RejectedBatchElementCount<br /><br /> BatchSize<br /><br /> LastBatchAction<br /><br /> CreationTime<br /><br /> ReleaseTime<br /><br /> BatchReleaseType<br /><br /> BatchServiceID<br /><br /> ActivationMessageID<br /><br /> ReleaseMessageID<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> BatchCorrelationID<br /><br /> BatchName<br /><br /> BatchID<br /><br /> LastModified|  
|BatchInterchangeActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverPartyName<br /><br /> SenderPartyName<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> 方向<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> BatchCorrelationID<br /><br /> LastModified|  
|BusinessMessageJournal|RecordID<br /><br /> ActivityID<br /><br /> MessageTrackingID<br /><br /> ActionType<br /><br /> ContainerActivityID<br /><br /> ContainerType<br /><br /> BTSInterchangeID<br /><br /> BTSMessageId<br /><br /> BTSServiceInstanceId<br /><br /> BTSHostName<br /><br /> RoutedToPartyName<br /><br /> LinkedMessageTrackingID<br /><br /> TimeCreated<br /><br /> LastModified|  
|FunctionalAckActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeActivityID<br /><br /> GroupControlNo<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> 方向<br /><br /> AckProcessingStatus<br /><br /> AckStatusCode<br /><br /> DeliveredTSCount<br /><br /> AcceptedTSCount<br /><br /> AckIcn<br /><br /> AckIcnDate<br /><br /> AckIcnTime<br /><br /> ErrorCode1<br /><br /> ErrorCode2<br /><br /> ErrorCode3<br /><br /> ErrorCode4<br /><br /> ErrorCode5<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> LastModified|  
|FunctionalGroupInfo|RecordID<br /><br /> ActivityID<br /><br /> InterchangeActivityID<br /><br /> GroupControlNo<br /><br /> FunctionalIDCode<br /><br /> TSCount<br /><br /> LastModified|  
|InterchangeAckActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> 方向<br /><br /> AckProcessingStatus<br /><br /> AckStatusCode<br /><br /> AckIcn<br /><br /> AckIcnDate<br /><br /> AckIcnTime<br /><br /> AckNoteCode1<br /><br /> AckNoteCode2<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> AckCorrelationId<br /><br /> LastModified|  
|InterchangeStatusActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> ReceiverPartyName<br /><br /> SenderPartyName<br /><br /> InterchangeDateTime<br /><br /> 方向<br /><br /> AckStatusCode<br /><br /> GroupCount<br /><br /> EdiMessageType<br /><br /> PortID<br /><br /> IsInterchangeAckExpected<br /><br /> IsFunctionalAckExpected<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> AckCorrelationId<br /><br /> TsCorrelationId<br /><br /> LastModified|  
|ResendJournalActivity|RecordID<br /><br /> ActivityID<br /><br /> TrackingActivityId<br /><br /> ResendIndex<br /><br /> ResendStatus<br /><br /> BTSInterchangeID<br /><br /> LastModified|  
|ResendTrackingActivity|RecordID<br /><br /> ActivityID<br /><br /> CorrelationId<br /><br /> AdapterPrefix<br /><br /> ResendCount<br /><br /> MaxResendCount<br /><br /> ResendInterval<br /><br /> MaxRetryCount<br /><br /> RetryInterval<br /><br /> MessageContentID<br /><br /> ResendTimeout<br /><br /> RetryTimeout<br /><br /> BTSInterchangeID<br /><br /> LastModified|  
|TransactionSetActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> 方向<br /><br /> ReceiverPartyName<br /><br /> SenderPartyName<br /><br /> ApplicationSender<br /><br /> ApplicationReceiver<br /><br /> GroupDateTime<br /><br /> GroupControlNo<br /><br /> TransactionSetId<br /><br /> DocType<br /><br /> TransactionSetControlNo<br /><br /> AckStatusCode<br /><br /> BatchProcessing<br /><br /> ProcessingDateTime<br /><br /> GroupOrdinal<br /><br /> TransactionSetOrdinal<br /><br /> MessageContentKey<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> TsCorrelationId<br /><br /> LastModified|  
  
## <a name="data-enumerations-in-the-bamprimaryimport-database"></a>BAMPrimaryImport 数据库中的数据枚举  
 某些 EDI 和 AS2 数据以枚举形式保存在 BAMPrimaryImport 数据库的表中。 这些数据在状态报告中将显示为文本。 其值如下所示：  
  
|字段|枚举值|  
|-----------|-----------------|  
|AckProcessingStatus|NotExpected = -1<br /><br /> 预期 = 0<br /><br /> Received = 1<br /><br /> 发送 = 2<br /><br /> Generated = 3|  
|AS2PartyRole|所有 = 0<br /><br /> Receiver = 1<br /><br /> Sender = 2|  
|BatchAction|Creation = 0<br /><br /> Activation = 1<br /><br /> ElementReference = 2<br /><br /> Release = 3<br /><br /> Override = 4<br /><br /> Termination = 5<br /><br /> Sent = 6<br /><br /> ToBeReleased = 7|  
|BatchStatus|所有 =-1<br /><br /> Defined = 0<br /><br /> 在职<br /><br /> Released<br /><br /> 已完成|  
|BatchType|ScheduleBased = 0<br /><br /> MessagesCountInGroup = 1<br /><br /> MessagesCountIn<br />交换 = 2<br /><br /> CharacterCount = 3<br /><br /> ExternalTrigger = 4|  
|方向|所有 = 0<br /><br /> Receive = 1<br /><br /> Send = 2|  
|DisplayAckStatusCode|All = 100<br /><br /> Accepted = 0<br /><br /> PartiallyAccepted = 1<br /><br /> Rejected = -1<br /><br /> AckExpected = 500<br /><br /> AckNotExpected = 600|  
|DispositionModifierExt<br />Description|Not Valued = 1<br /><br /> Authentication Failed = 2<br /><br /> Decryption Failed = 3<br /><br /> 没有足够的消息<br />安全 = 4<br /><br /> Integrity Check Failed = 5<br /><br /> 意外的处理 <br />错误 = 6|  
|DispositionModifierExt<br />类型|Not Valued = 1<br /><br /> Error = 2<br /><br /> Warning = 3|  
|EdiMessageType|X12，<br /><br /> Edifact,<br /><br /> Unknown|  
|IsMdnExpected|MDN is not expected = 0<br /><br /> MDN is expected = 1|  
|MdnDispositionType|Processed = 1<br /><br /> Failed = 2|  
|MdnProcessingStatus|所有 = 0<br /><br /> Processed = 1<br /><br /> Failed = 2<br /><br /> Expected = 3<br /><br /> Not Expected = 4|  
|MessageEncryptionType|Message is not encrypted = 0<br /><br /> Message is encrypted = 1|  
|MessageSignatureType|Message is not signed = 0<br /><br /> Message is signed = 1|  
|MicAlgorithmType|Unknown type = -1<br /><br /> SHA1 = 1<br /><br /> MD5 = 2|  
  
## <a name="businessmessagejournal-bam-activity"></a>BusinessMessageJournal BAM Activity  
 通过 BusinessMessageJournal BAM 活动，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以将收到的包含事务集的 EDI 交换与包含相同事务集的传出批交换相关联。 有关详细信息，请参阅[关联传出批的传入事务集](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md)。  
  
##  <a name="BKMK_Query"></a>查询 EdiMessageContent 表  
 在 BizTalkDTADb 数据库中的 EdiMessageContent 表中，可存储消息负载以及消息元数据。 通过自定义状态报告，您可以查询 EdiMessageContent 表以显示消息内容。 这与通过本产品中的某些状态报告显示消息内容的方法类似，例如使用 AS2 消息和相关 MDN 状态报告显示消息线路格式的方法。  
  
 使用自定义 BAM 活动中与 EdiMessageContent 表中的 ContentKey 列对应的键列，可以从自定义 BAM 活动链接到 EdiMessageContent 表。 例如，要从 AS2MessageActivity BAM 活动链接到 EdiMessageContent 表，可使用 MessagePayloadContentKey 列或 MessageWireContentKey 列链接到 ContentKey 列。  
  
|表|列|  
|-----------|-------------|  
|EdiMessageContent<br /><br /> （在 BizTalkDTADb 数据库中）|ContentKey<br /><br /> MessageFormat<br /><br /> ContentType<br /><br /> Charset<br /><br /> TimeCreated<br /><br /> TimeInserted<br /><br /> IsOrphaned<br /><br /> ContentBinary|  
  
## <a name="see-also"></a>另请参阅  
 [如何将数据存储用于 EDI 和 AS2 状态报表](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)   
 [将传入事务集与传出批相关联](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md)