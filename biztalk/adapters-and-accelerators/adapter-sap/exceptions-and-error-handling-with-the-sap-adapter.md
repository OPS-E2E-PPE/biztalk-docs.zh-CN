---
title: 异常和错误处理与 SAP 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions and error handling
- error handling, troubleshooting
- troubleshooting, exceptions and error handling
ms.assetid: 598a25c5-6905-4c0c-835b-159d827b2269
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5439ae9cc58dfbb649fefd7ae3f18348502bcd48
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991622"
---
# <a name="exceptions-and-error-handling-with-the-sap-adapter"></a>异常和错误处理与 SAP 适配器
列出了异常的[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]引发。 这些可以包含：  

- 内部异常，这是.NET Framework 将引发系统异常  

- LOB 客户端库将引发一个 LOB 异常。  

  有关内部异常的详细信息，请参阅.NET Framework 或 SAP 文档。 异常还包含可能帮助解决此问题的详细的错误消息。  

## <a name="exception-descriptions"></a>异常说明  

|异常|可能的原因说明|  
|---------------|---------------------------------|  
|ObjectDisposedException|适配器客户端尝试访问响应 XMLReader 后已被释放时，适配器会引发此异常。|  
|XmlReaderGenerationException|当无法从输出消息生成 XmlReader 时，适配器会引发此异常。 这也可能是由于 SAP 系统从接收的数据的存在一些问题。 查找内部异常和错误消息以了解更多信息。|  
|InvalidUriException|当连接 URI 没有连接字符串所需的组件时，引发此异常。|  
|ConnectionException|连接到 SAP 系统时出现问题时，或者基础连接将变为无效，因为 SAP 系统上出现错误或由于网络问题，则会引发此异常。|  
|TimeoutException|如果指定的操作的超时期满，引发此异常。 内部异常包含指定的超时的原因不足够的细节。|  
|XmlReaderParsingException|如果它不支持指定的类型，或不正确的值指定的类型，则适配器会引发此异常。 此外，输入的 XML 可能不正确。 不正确的值包括其中超出了文本或最大数字的最长的情况。 输入的 XML 可能不正确的操作名称或命名空间是否不正确。|  
|RFCException （派生自 AdapterException）|如果错误来自 SAP 系统，该适配器会引发此异常。 内部异常是从 SAP 系统收到的实际异常。|  
|UnsupportedOperationException|当适配器客户端指定操作无效时，适配器会引发此异常。|  
|MetadataException|如果元数据检索、 浏览或搜索过程中出错，则适配器会引发此异常。|  

## <a name="see-also"></a>请参阅  
[SAP 适配器疑难解答](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)