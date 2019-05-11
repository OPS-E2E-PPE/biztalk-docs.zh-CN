---
title: 消息引擎接口 |Microsoft Docs
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
ms.openlocfilehash: 08b8d795b6df72f3e555f527e3d995cab1d288e8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394530"
---
# <a name="messaging-engine-interfaces"></a>消息引擎接口
适配器可以使用三种公共接口来允许与消息引擎的交互。 下面几部分将概要介绍这些公共接口。  
  
## <a name="ibttransportproxy"></a>IBTTransportProxy  
 适配器始终通过使用自己的传输代理与消息引擎交互。 该传输代理用于创建批、获取消息工厂和向引擎注册独立接收器等操作。  
  
## <a name="ibttransportbatch"></a>IBTTransportBatch  
 此接口由消息引擎提供，用于定义适配器可用来操作消息批的方法。 消息引擎通过异步方式处理批。  
  
## <a name="ibtdtccommitconfirm"></a>IBTDTCCommitConfirm  
 在批上使用显式 Microsoft 分布式事务处理协调器 (MSDTC) 事务的适配器必须使用此接口来通知引擎该事务的结果。