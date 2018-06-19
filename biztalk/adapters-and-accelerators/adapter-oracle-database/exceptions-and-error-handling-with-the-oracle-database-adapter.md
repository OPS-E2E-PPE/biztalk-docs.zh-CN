---
title: 异常和错误处理使用 Oracle 数据库适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exception, LOB
- exception, inner
- exceptions, error handling
- error handling, exceptions
ms.assetid: df9a1244-63cd-438e-8a06-99383fbeba2c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bd85c53a1e13d127883e463cafec742f2751722
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215165"
---
# <a name="exceptions-and-error-handling-with-the-oracle-database-adapter"></a>异常和错误处理使用 Oracle 数据库适配器
本部分列出的异常，[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]引发。 这些可以包含：  
  
-   内部异常，这是.NET Framework 引发系统异常。  
  
-   LOB 客户端库引发的 LOB 异常。  
  
 有关内部异常的详细信息，请参阅相应的.NET Framework 或 Oracle 文档。 异常还包含详细的错误消息，以解决此问题可帮助。  
  
|异常|可能的原因说明|  
|---------------|---------------------------------|  
|XmlReaderParsingException|如果不支持指定的类型，或如果为类型指定值不正确，则适配器会引发此异常。 此外，输入 XML 可能不正确。 不正确的值包括其中超出了文本或最大的数字的最长的情况。 输入 XML 可能不正确，如果操作名称或命名空间不正确。|  
|UnsupportedOperationException|适配器适配器客户端指定了无效的操作会引发此异常。|  
|ArgumentException|如果为参数指定值不正确，则适配器会引发此异常。|  
|NotImplementedException|如果未实现 XMLReader 读取器中的某些方法，该适配器会引发此异常。|  
|ArgumentNullException|如果未指定必需的参数，该适配器会引发此异常。|  
|ArgumentOutOfRangeException|如果它尝试访问不存在实体或超出范围实体，该适配器会引发此异常。|  
|XmlReaderGenerationException|无法从输出消息生成 XmlReader 时，适配器会引发此异常。|  
|MetadataException|如果元数据检索、 浏览或搜索期间出现错误，该适配器会引发此异常。|  
|CredentialsException|如果没有问题检索或使用安全令牌，或者如果未指定所需的凭据，该适配器会引发此异常。|  
|InvalidUriException|如果连接 URI 没有连接字符串所需的组件，该适配器会引发此异常。|  
|ConnectionException|如果没有连接到 Oracle 数据库使用 ODP.NET 时出现问题，该适配器会引发此异常。 内部异常包含 Oracle 异常。|  
|TimeoutException|如果结束操作指定的超时值，该适配器会引发此异常。 内部异常包含指定的超时的原因不足够的详细信息。|  
|ListenerException|如果在从目标系统接收消息的问题，该适配器会引发此异常。 此消息表示与 Oracle 侦听器相关问题。 内部异常都有问题的详细信息。|  
|TargetSystemException|如果 Oracle 将返回错误或无效的响应，则适配器将引发此异常。 内部异常包含 Oracle 运行时异常。|  
|InvalidOperationException|如果适配器尝试执行无效操作目标系统上的，该适配器会引发此异常。 内部异常将包含所执行的无效操作的详细信息。|  
|OverflowException|如果执行操作时包含 Oracle 内部数据集或弱类型 REF CURSOR 的数值数据类型，该适配器会引发此异常，将为无法相应的.NET 类型中容纳这些 Oracle 数值数据类型指定较大的值。|  
  
## <a name="see-also"></a>另请参阅  
[对 Oracle 数据库适配器进行故障排除](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)