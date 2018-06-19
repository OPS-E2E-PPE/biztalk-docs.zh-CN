---
title: 异常和错误处理与 SAP 适配器 |Microsoft 文档
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
ms.openlocfilehash: 043f76f7fc730430610b7598bbab208ca8b135a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216845"
---
# <a name="exceptions-and-error-handling-with-the-sap-adapter"></a>异常和错误处理与 SAP 适配器
列出了异常，[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]引发。 这些可以包含：  
  
-   内部异常，这是.NET Framework 引发系统异常  
  
-   LOB 客户端库引发的 LOB 异常。  
  
 有关内部异常的详细信息，请参阅.NET Framework 或 SAP 文档。 异常还包含详细的错误消息可能有助于解决问题。  

## <a name="exception-descriptions"></a>异常说明  
|异常|可能的原因说明|  
|---------------|---------------------------------|  
|ObjectDisposedException|适配器客户端尝试访问响应 XMLReader 之后它已被释放, 时，适配器会引发此异常。|  
|XmlReaderGenerationException|无法从输出消息生成 XmlReader 时，适配器会引发此异常。 这也可能是由于 SAP 系统从接收的数据的一些问题。 查找内部异常和错误消息以了解更多信息。|  
|InvalidUriException|当连接 URI 没有连接字符串所需的组件时，引发此异常。|  
|ConnectionException|连接到 SAP 系统时出现问题时，或者如果基础的连接将变为无效，是由于 SAP 系统上发生错误或者是由于网络问题，将引发此异常。|  
|TimeoutException|结束操作指定的超时值时，引发此异常。 内部异常包含指定的超时的原因不足够的详细信息。|  
|XmlReaderParsingException|如果不支持指定的类型，或如果为类型指定值不正确，则适配器会引发此异常。 此外，输入 XML 可能不正确。 不正确的值包括其中超出了文本或最大的数字的最长的情况。 输入 XML 可能不正确，如果操作名称或命名空间不正确。|  
|RFCException （从 AdapterException 派生）|如果从 SAP 系统收到错误，该适配器会引发此异常。 内部异常是从 SAP 系统收到实际异常。|  
|UnsupportedOperationException|适配器适配器客户端指定了无效的操作会引发此异常。|  
|MetadataException|如果元数据检索、 浏览或搜索期间出现错误，该适配器会引发此异常。|  
  
## <a name="see-also"></a>另请参阅  
[故障排除 SAP 适配器](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)