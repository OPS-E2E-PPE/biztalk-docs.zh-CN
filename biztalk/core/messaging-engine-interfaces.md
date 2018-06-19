---
title: 消息传送引擎接口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14241db3-edcf-4449-9ec8-2171a14496c0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a135505240e94fb42e5810a3e7ac71d4c99c34a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263285"
---
# <a name="messaging-engine-interfaces"></a>消息传递引擎接口
适配器可以使用三种公共接口来允许与消息引擎的交互。 下面几部分将概要介绍这些公共接口。  
  
## <a name="ibttransportproxy"></a>IBTTransportProxy  
 适配器始终通过使用自己的传输代理与消息引擎交互。 该传输代理用于创建批、获取消息工厂和向引擎注册独立接收器等操作。  
  
## <a name="ibttransportbatch"></a>IBTTransportBatch  
 此接口由消息引擎提供，用于定义适配器可用来操作消息批的方法。 消息引擎通过异步方式处理批。  
  
## <a name="ibtdtccommitconfirm"></a>IBTDTCCommitConfirm  
 在批上使用显式 Microsoft 分布式事务处理协调器 (MSDTC) 事务的适配器必须使用此接口来通知引擎该事务的结果。