---
title: 异常和错误处理与 Oracle 数据库适配器 |Microsoft Docs
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
ms.openlocfilehash: 5496eb567e71fdd7d01e36445f21a83dfc7a3ff1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376582"
---
# <a name="exceptions-and-error-handling-with-the-oracle-database-adapter"></a>异常和错误处理与 Oracle 数据库适配器
本部分列出了异常的[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]引发。 这些可以包含：  
  
- 内部异常，这是.NET Framework 将引发系统异常。  
  
- LOB 客户端库将引发一个 LOB 异常。  
  
  有关内部异常详细信息，请参阅相应的.NET Framework 或 Oracle 文档。 异常还包含详细的错误消息，可帮助以解决此问题。  
  
|异常|可能的原因说明|  
|---------------|---------------------------------|  
|XmlReaderParsingException|如果它不支持指定的类型，或不正确的值指定的类型，则适配器会引发此异常。 此外，输入的 XML 可能不正确。 不正确的值包括其中超出了文本或最大数字的最长的情况。 输入的 XML 可能不正确的操作名称或命名空间是否不正确。|  
|UnsupportedOperationException|当适配器客户端指定操作无效时，适配器会引发此异常。|  
|ArgumentException|如果为参数指定值不正确，则适配器会引发此异常。|  
|NotImplementedException|如果未实现 XMLReader 读取器中的一些方法，该适配器会引发此异常。|  
|ArgumentNullException|如果未指定必需的参数，则适配器会引发此异常。|  
|ArgumentOutOfRangeException|如果它尝试访问不存在实体或范围扩展的实体，则适配器会引发此异常。|  
|XmlReaderGenerationException|当无法从输出消息生成 XmlReader 时，适配器会引发此异常。|  
|MetadataException|如果元数据检索、 浏览或搜索过程中出错，则适配器会引发此异常。|  
|CredentialsException|如果没有问题检索或使用安全令牌，或如果未指定所需的凭据，则适配器会引发此异常。|  
|InvalidUriException|如果连接 URI 不具有所需的组件的连接字符串，该适配器会引发此异常。|  
|ConnectionException|如果连接到 Oracle 数据库使用 ODP.NET 问题，适配器会引发此异常。 内部异常包含的 Oracle 异常。|  
|TimeoutException|如果过期超过指定的操作的超时值，则适配器会引发此异常。 内部异常包含指定的超时的原因不足够的细节。|  
|ListenerException|如果在从目标系统接收消息的问题，适配器会引发此异常。 此消息表示存在到 Oracle 侦听器有关的问题。 内部异常有问题的详细信息。|  
|TargetSystemException|如果 Oracle 返回错误或无效的响应，则适配器会引发此异常。 内部异常包含 Oracle 运行时异常。|  
|InvalidOperationException|如果尝试执行无效操作在目标系统上的适配器，适配器会引发此异常。 内部异常包含所执行的无效操作的具体情况。|  
|OverflowException|适配器会引发此异常，如果执行操作时包含内部数据集或弱类型化 REF CURSOR 的 Oracle 数值数据类型，不能相应的.NET 类型中容纳这些 Oracle 数值数据类型指定较大的值。|  
  
## <a name="see-also"></a>请参阅  
[Oracle 数据库适配器疑难解答](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)