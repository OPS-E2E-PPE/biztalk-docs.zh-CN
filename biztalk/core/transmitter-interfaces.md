---
title: 发射器接口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ffa6db3b-739e-438c-b410-8823a20eed82
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e922cd2526002306928b2eae3418185986ed741
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279717"
---
# <a name="transmitter-interfaces"></a>发射器接口
除了强制适配器接口，传输 （发送） 适配器，需要实现**IBTTransmitter**它们是否非批处理或**IBTBatchTransmitter**如果按批处理。  
  
 下图显示了按批处理和不按批处理的发送适配器都需要实现的接口。  
  
 ![](../core/media/transmitterinterfaces.gif "TransmitterInterfaces")