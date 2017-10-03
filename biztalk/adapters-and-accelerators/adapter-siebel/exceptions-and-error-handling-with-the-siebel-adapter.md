---
title: "异常和错误处理，并在 Siebel 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- error handling, troubleshooting
- exceptions, troubleshooting
- troubleshooting, exceptions and error handling
ms.assetid: d46e908f-0715-43e2-879b-f5d0beb9bc64
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 743e2a0f03e35282c24a506ff37e9d774f0b7505
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="exceptions-and-error-handling-with-the-siebel-adapter"></a>异常和错误处理，并在 Siebel 适配器
## <a name="exception-list"></a>异常列表
引发的异常[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。 这些可以包含：  
  
-   内部异常，这是.NET Framework 引发系统异常  
  
-   LOB 客户端库引发的 LOB 异常。  
  
 有关内部异常的详细信息，请参阅相应的.NET Framework 或 Siebel 文档。 该异常还包含详细的错误消息，以解决此问题可帮助。 请注意，此处提及的例外列表中的不完整。  
  
|异常|可能的原因错误说明|  
|---------------|---------------------------------------|  
|ConnectionException|如果无法建立的连接或关闭现有连接到 Siebel 系统，该适配器会引发此异常。|  
|CredentialsException|如果适配器客户端未指定用户名或密码以连接到 Siebel 系统，该适配器将引发此异常。|  
|MetadataException|如果它无法检索有关 Siebel 项目的元数据，该适配器会引发此异常。|  
|XmlReaderParsingException|如果要在 Siebel 系统中，调用操作的适配器客户端提供的输入的信息不完整或不正确，则适配器会引发此异常。|  
|XmlReaderGenerationException|如果无法生成 Siebel 系统中执行的操作的输出，该适配器会引发此异常。|  
|TargetSystemException|适配器会引发此异常，如果 Siebel COM api，该适配器使用到 API 接口 Siebel 系统，则引发一个异常。 内部异常包含 Siebel COM API 所引发的异常。|  
  
## <a name="see-also"></a>另请参阅  
 [为 Siebel eBusiness 应用程序了解的 BizTalk Adapter](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)   
[解决在 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)