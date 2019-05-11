---
title: 发射器接口 |Microsoft Docs
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
ms.openlocfilehash: 9e0bab66be2867d8f0117d951b706953f2b541a2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243093"
---
# <a name="transmitter-interfaces"></a>发射器接口
除了必需的适配器接口，传输 （发送） 适配器，需要实现**IBTTransmitter**它们是否不按批处理或**IBTBatchTransmitter**如果进行批处理。  
  
 下图显示了按批处理和非批处理的发送适配器需要实现的接口。  
  
 ![](../core/media/transmitterinterfaces.gif "TransmitterInterfaces")