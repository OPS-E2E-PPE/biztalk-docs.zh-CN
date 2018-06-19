---
title: AS2 事件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c9de140d-8961-4c19-a2e5-14631016541f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 824fda0d49ddfd9c5d6f6c12a379568775b8d160
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233589"
---
# <a name="as2-events"></a>AS2 事件
下表列出了 AS2 处理期间事件日志中可能发布的事件消息。  
  
> [!NOTE]
>  下表中列出的 AS2 错误有关的详细信息，请参阅[EDI 和 AS2 事件](../core/edi-and-as2-events.md)。  
  
|错误代码|条件|  
|----------------|---------------|  
|AS2DecoderMissingDispositionNotificationOptionsHTTPHeaderError|AS2 解码器无法定位生成 MDN 所必需的 Disposition-Notification-Options HTTP 标头。|  
|SynchronousMdnRequestedOnOneWayReceivePortError|配置错误。  在单向 HTTP 接收端口上请求了同步 MDN。|  
|SynchronousMdnRequestedOnOneWaySendPortError|配置错误。  在单向 HTTP 发送端口上请求了同步 MDN。|  
|EncryptionCertNotConfiguredError|尚未为 AS2 参与方配置加密证书。  AS2-从： {0} AS2-到： {1}|  
|AS2DecoderPartySigningConfigurationError|配置错误。  消息签名与预期的值不匹配。  请与发送合作伙伴联系，以验证签名使用情况。  AS2-从:"{0}"AS2-到:"\ {1 \}"MessageID:"\ {2 \}"|  
|AS2DecoderExceptionEncounteredDuringProcessing|AS2 解码器在处理期间遇到异常。  消息和异常的详细信息如下所示： AS2-从:"{0}"AS2-到:"\ {1 \}"MessageID:"\ {2 \}"MessageType:"{3}"异常:"\ {4\}"|  
|AS2DecoderMdnMicFailureDuringProcessing|AS2 解码器在验证 MDN 中返回的 MIC 值时处理失败。  MDN 消息的详细信息如下所示： AS2-从:"{0}"AS2-到:"\ {1 \}"MessageID:"\ {2 \}"OriginalMessageID:"\ {3\}"|  
|AS2DecoderMdnSigningMismatchFailureDuringProcessing|AS2 解码器处理失败，因为 MDN 签名与我们的请求不匹配。  MDN 消息的详细信息如下所示： AS2-从:"{0}"AS2-到:"\ {1 \}"MessageID:"\ {2 \}"OriginalMessageID:"\ {3\}"|  
|AS2DecoderMdnProcessingFailureReturned|AS2 解码器处理失败，因为 MDN 指示 AS2 消息处理失败。  MDN 消息的详细信息如下所示： AS2-从:"{0}"AS2-到:"\ {1 \}"MessageID:"\ {2 \}"OriginalMessageID:"\ {3\}"|  
|AS2InvalidQuotedStringHeaderError|遇到无效的引用 HTTP 标头。  详细信息如下所示： 标头名称:"{0}"标头值:"{1}"|  
|AS2MicDataStoreDuplicateMicError|错误 Mic 条目已存在。|  
|AS2StreamingNonSeekableStreamError|这是一个无法找到的流。|  
|AS2StreamingSetLengthError|无法设置此流的长度。|  
|AS2StreamingWriteToReadonlyStreamError|这是一个只读流。|  
|AS2StreamingMethodNotImplementedError|方法或操作未实现。|  
|BtsMimeExceptionEncounteredDuringMessageDecoding|尝试对 AS2 消息进行解码时遇到 BTS MIME 错误。  AS2-从: {0}，AS2-到： {1}，MessageId: {2}，错误： {3}|  
|AS2DecoderPartyEncryptionConfigurationError|配置错误。  消息加密与预期值不匹配。  请与发送合作伙伴联系，以验证加密使用情况。  AS2-从:"{0}"AS2-到:"\ {1 \}"MessageID:"\ {2 \}"|  
|AS2DecoderPartySignatureError|配置错误。  消息签名与为此参与方配置的签名不匹配。  请与发送合作伙伴联系，以验证使用的证书。  AS2-从:"{0}"AS2-到:"\ {1 \}"MessageID:"\ {2 \}"|  
|InvalidAgreementAS2FromName|此 AS2 交换的参与方必须包含 AS2-From 的值。|  
|InvalidAgreementAS2ToName|此 AS2 交换的参与方必须包含 AS2-To 的值。|  
|UnsupportedAS2HashAlgorithmError|不支持在 AS2 消息中指定的哈希算法。|  
|UnableToLocateAS2PartyError|找不到访问方使用限定符： {0} 方： {1}。  错误： {2}|  
|UnableToLocateAS2PartyByPartyNameError|无法访问方使用方: {0}。|  
|UnableToLocateAS2PartyBySendPortNameError|无法访问方使用发送端口： {0} 错误： {1}。|  
|InvalidAS2FromNameConfiguredError|无效的 AS2-从配置为当事方名称： {0} 值： {1}|  
|InvalidAS2ToNameConfiguredError|无效的 AS2-到配置为当事方名称： {0} 值： {1}|  
|InvalidAS2FromNameHeaderReceivedError|收到的 AS2-From 头部无效。  值： {0}|  
|InvalidAS2ToNameHeaderReceivedError|收到的 AS2-To 头部无效。  值： {0}|  
|MissingAS2FromHeaderError|收到的 AS2 消息不包含 AS2-From 头部。|  
|MissingAS2ToHeaderError|收到的 AS2 消息不包含 AS2-To 头部。|  
|InvalidDispositionNotificationOptionToError|处理通知选项值:"{0}"无效。  {1}|  
|InvalidReceiptDeliveryOptionError|回执送达选项值:"{0}"无效。  {1}|  
|InvalidOrMissingASN1DataLengthHeader|解压缩处理期间 ASN.1 数据长度字段无效或缺失。|  
|InvalidOrMissingASN1TrailingBytes|解压缩处理期间尾部 ASN.1 CMS 压缩结构字节无效或缺失。|  
|InvalidASN1CompressedStructureEncountered|解压缩处理期间遇到无效的 ASN.1 压缩结构。|  
|InvalidOrMissingDataHeaderEncountered|解压缩处理期间 ASN.1 压缩头部无效或缺失。|  
|InvalidOptionalZLibFieldEncountered|解压缩处理期间遇到无效的 ASN.1 ZLib 压缩字段。|  
|InvalidOrMissingDataOIDEncountered|解压缩处理期间 ASN.1 数据 OID 无效或缺失。|  
|InvalidOrMissingZLibOIDEncountered|解压缩处理期间 ASN.1 ZLib OID 无效或缺失。|  
|InvalidOrMissingCompressedDataOIDEncountered|解压缩处理期间 ASN.1 压缩数据 OID 无效或缺失。|  
|InvalidAdler32ChecksumInCompressedMessageError|遇到无效的 Adler32 校验和。|  
|UnsupportedOctetStringLengthEncountered|遇到不支持的 Octet 字符串长度。  支持的最大 octet 长度为 4。|  
|DecompressionFailedError|处理压缩的 AS2 消息时解压缩失败。  错误： {0}|  
|DecryptionFailedError|解密 AS2 消息时出错。|  
|IntegrityCheckFailedError|验证 AS2 消息时出错。  请确保使用的证书没有过时或被吊销。|  
|EncryptionCertificateHasBeenRevokedError|用于加密消息的证书已经被吊销。 证书指纹： {0}|  
|DecryptionCertificateHasBeenRevokedError|用于解密消息的证书已经被吊销。 证书指纹： {0}|  
|SigningCertificateHasBeenRevokedError|用于对消息进行签名的证书已经被吊销。 证书指纹： {0}|  
|SignatureCertificateHasBeenRevokedError|用于对消息进行签名的证书已经被吊销。 证书指纹： {0}|  
|CertificateMissingError|无法在本地证书存储中定位用于对消息签名的证书。 证书指纹： {0}|  
|EmptyContentOnAS2MessageEncountered|收到空的 AS2 消息。  该消息将被挂起。|  
|AS2FromMatchesAS2ToError|AS2-From 值匹配 AS2-To 值。|  
|GenericEdiIntException|出现 EdiInt 异常。|  
|BtsMimeExceptionEncounteredDuringMessageEncoding|尝试对消息进行编码时遇到 BTS MIME 错误。  错误: {0}，HResult: \ {1 \}|  
|BtsMimeGeneralExceptionEncounteredDuringMessageEncoding|尝试对消息进行编码时遇到 BTS MIME 错误。  错误： {0}|  
|AS2StatusReportingExceptionEncountered|尝试生成 AS2 状态报告时遇到错误。  错误： {0}|