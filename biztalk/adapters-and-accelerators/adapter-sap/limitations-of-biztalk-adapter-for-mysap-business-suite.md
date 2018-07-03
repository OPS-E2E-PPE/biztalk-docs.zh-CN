---
title: 用于 mySAP Business Suite 的 BizTalk 适配器的限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, limitations of
- IDOC, sending an IDOC to an SAP system
ms.assetid: 1ca1e0cf-7ae7-4a8b-8363-e5f3746e8e26
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f289d1f70005e8b4caa0e7c739522cc5590bca58
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973710"
---
# <a name="limitations-of-biztalk-adapter-for-mysap-business-suite"></a>用于 mySAP Business Suite 的 BizTalk 适配器的限制

## <a name="limitations-list"></a>限制列表
以下已知的限制[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]:  
  
- [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不兼容的 Microsoft BizTalk 适配器用于 mySAP Business Suite，以前版本的适配器。 此版本的适配器不支持发送和接收具有使用适配器的早期版本生成的架构的消息。  
  
- [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]具有复杂的参数类型，包括 ITAB II （分层） 的表类型中不支持 Rfc。  
  
- [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不支持 Rfc 具有自定义 ABAP 类型。  
  
- 由于基础客户端库，超时处理问题[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不支持命令，并连接超时。  
  
- 如果更改运行 BizTalk Server 主机的计算机的系统时间，时间不能在 BizTalk Server 主机中自动更新。 这可能会导致不正确的行为，使用 BizTalk Server 接收端口的入站操作。 解决此问题，必须重新启动主机实例的接收端口中，更改运行它的计算机的系统时间之后。  
  
## <a name="see-also"></a>请参阅  
 [了解用于 mySAP Business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)