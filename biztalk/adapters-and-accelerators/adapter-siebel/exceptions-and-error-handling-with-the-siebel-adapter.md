---
title: 异常和错误处理与 Siebel 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error handling, troubleshooting
- exceptions, troubleshooting
- troubleshooting, exceptions and error handling
ms.assetid: d46e908f-0715-43e2-879b-f5d0beb9bc64
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 149f69681e66a9be39a2586563d6d6a4df649f1d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371743"
---
# <a name="exceptions-and-error-handling-with-the-siebel-adapter"></a>异常和错误处理与 Siebel 适配器
## <a name="exception-list"></a>异常列表
引发的异常[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。 这些可以包含：  
  
- 内部异常，这是.NET Framework 将引发系统异常  
  
- LOB 客户端库将引发一个 LOB 异常。  
  
  有关内部异常的详细信息，请参阅相应的.NET Framework 或 Siebel 文档。 该异常还包含详细的错误消息，可帮助以解决此问题。 请注意此处提及的异常的列表并不全面。  
  
|异常|可能的原因错误说明|  
|---------------|---------------------------------------|  
|ConnectionException|如果无法建立的连接或关闭现有连接到 Siebel 系统，该适配器会引发此异常。|  
|CredentialsException|如果适配器客户端不指定用户名或密码以连接到 Siebel 系统，该适配器会引发此异常。|  
|MetadataException|未能检索 Siebel 项目的元数据时，适配器会引发此异常。|  
|XmlReaderParsingException|如果适配器客户端，若要在 Siebel 系统中，调用的操作提供的输入的信息不完整或不正确，则适配器会引发此异常。|  
|XmlReaderGenerationException|如果无法生成在 Siebel 系统中执行的操作的输出，则适配器会引发此异常。|  
|TargetSystemException|适配器会引发此异常，如果 Siebel COM API，则适配器将使用到该接口与 Siebel 系统，则引发一个异常。 内部异常包含由 Siebel COM API 引发的异常。|  
  
## <a name="see-also"></a>请参阅  
 [了解用于 Siebel eBusiness 应用程序的 BizTalk 适配器](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)   
[Siebel 适配器疑难解答](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)