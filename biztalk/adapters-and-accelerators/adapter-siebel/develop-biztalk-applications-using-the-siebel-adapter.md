---
title: 开发使用 Siebel 适配器的 BizTalk 应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 08/02/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk applications, developing
- developing, BizTalk applications
- CBR
- Content-Based Routing
ms.assetid: 1a2a9765-305c-44b2-aed7-5437725e4c19
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8267c07027d9994b0115ebaf49fde96e76f2716
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22221925"
---
# <a name="develop-biztalk-applications-using-the-siebel-adapter"></a>开发使用 Siebel 适配器的 BizTalk 应用程序

## <a name="overview"></a>概述
开发 BizTalk 应用程序涉及到创建中的 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成 XML 架构。 一旦你已生成架构，你可以使用基于内容的路由 (CBR)，或创建 BizTalk 业务流程，以发送和接收符合生成架构的消息。  
  
 CBR 可以用于的方案发送到 Siebel 系统的消息不需要任何密集型处理。 例如，如果你知道接收端口将接收仅特定类型的消息，可以将筛选器添加到要将路由到发送端口筛选器表达式匹配的消息的发送端口中。  
  
 在 BizTalk 业务流程中创建发送和接收端口发送和接收消息，并从[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，这反过来将消息发送到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 本部分提供有关使用 BizTalk 业务流程执行对 Siebel 系统使用的操作的信息[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]反过来使用[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]与 WCF 绑定交互。  

## <a name="before-you-begin"></a>开始之前  

* 若要使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，始终将**EnableBizTalkCompatibilityMode**属性绑定到**True**。 有关步骤，请参阅[为 Siebel 配置的绑定属性](../../adapters-and-accelerators/adapter-siebel/configure-the-binding-properties-for-siebel.md)。
  
* [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]BizTalk Server 管理控制台中未自动列出。 这是因为[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]是 WCF 自定义绑定。 

* 若要生成元数据，使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。 不要使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 有关使用说明[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，请参阅[获取 Visual Studio 中的 Siebel 操作的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)。   

  
## <a name="see-also"></a>另请参阅  
[开发 Siebel 应用程序](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)