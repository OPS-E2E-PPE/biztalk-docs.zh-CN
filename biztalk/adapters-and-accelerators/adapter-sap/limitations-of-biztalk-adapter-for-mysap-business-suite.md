---
title: 为 mySAP Business Suite 的 BizTalk Adapter 限制 |Microsoft 文档
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
ms.openlocfilehash: 1d392178cd49918151f0ad86c73a5fcba712d6b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217077"
---
# <a name="limitations-of-biztalk-adapter-for-mysap-business-suite"></a>为 mySAP Business Suite 的 BizTalk Adapter 限制

## <a name="limitations-list"></a>限制列表
以下已知的限制[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]:  
  
-   [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不兼容与 Microsoft BizTalk 适配器为 mySAP Business Suite，以前的版本中的适配器。 此版本的适配器不支持发送和接收具有使用适配器的早期版本生成的架构的消息。  
  
-   [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不支持 Rfc 对具有复杂的参数类型，包括 ITAB II （分层） 的表类型。  
  
-   [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不支持具有自定义的 ABAP 类型的 Rfc。  
  
-   由于出现超时处理基础的客户端库，问题[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不支持命令和连接超时。  
  
-   如果你更改运行 BizTalk Server 主机的计算机的系统时间，时间不能在 BizTalk Server 主机中自动更新。 这可能导致不正确的行为，使用 BizTalk Server 接收端口的入站操作。 一种解决方法，你必须重新启动后已更改运行它的计算机的系统时间具有接收端口、 主机实例。  
  
## <a name="see-also"></a>另请参阅  
 [为 mySAP Business Suite 了解 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)