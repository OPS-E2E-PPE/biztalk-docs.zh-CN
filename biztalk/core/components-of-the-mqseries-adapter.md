---
title: MQSeries 适配器的组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, BizTalk component
- MQSeries adapters, components
- MQSeries components, MQSeries adapters
- BizTalk components
- MQSeries adapters, MQSeries component
ms.assetid: 923974cb-371d-47dc-99a7-2f7b93f60ada
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c6a97bd38a68eef866549f980624a92ee2b3143
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391635"
---
# <a name="components-of-the-mqseries-adapter"></a>MQSeries 适配器的组件
MQSeries 适配器使用两个组件之间进行文档传输[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 MQSeries Server for Windows。  
  
- **BizTalk 组件。** Microsoft 在同一台计算机上安装此组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 此组件与 BizTalk Server 进行通信。  
  
- **MQSeries 组件。** 对于 Windows MQSeries 服务器上安装此组件。 MQSeries Server for Windows 上运行[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]。 此组件 （称为 MQSAgent） 与 IBM MQSeries 服务器进行通信。  
  
  > [!NOTE]
  >  MQSeries 适配器的 MQSAgent 组件是支持的运行 MQSeries Server 5.3、 CSD10 或更高版本，并在 Windows 上的 WebSphere MQSeries Server 6.0。  
  
  下图概述了该适配器的典型用法。  
  
  ![文档 MQSeries Server 和 BizTalk 之间的流](../core/media/bts-dev-mqadapterflow.gif "BTS_Dev_MQAdapterFlow")  
  
  MQSeries 适配器是一种连接解决方案，使您可以使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的企业中使用 MQSeries 作为所选的消息传送标准。 开发此解决方案时的部分原因，由以下问题：  
  
- 对于简单的安装和配置以及 MQSeries 连接解决方案如何适应客户请求  
  
- 支持的消息大小最大 100 MB  
  
- 提供 MQSeries 支持  
  
- 提供的 MQSeries 消息插连接解决方案 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
  MQSeries 适配器是一个重要的补充[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为各种通信协议标准提供了一组侦听器接收服务套件。 侦听器将一种协议，例如 HTTP、 FTP 或 MQSeries，附加到的企业应用程序集成 (EAI)，企业到企业或应用程序集成贸易关系。  
  
## <a name="see-also"></a>请参阅  
 [MQSeries 适配器体系结构](../core/mqseries-adapter-architecture.md)   
 [MQSeries 适配器概述](../core/what-is-the-mqseries-adapter.md)