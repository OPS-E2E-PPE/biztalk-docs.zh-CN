---
title: "发射器接口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ffa6db3b-739e-438c-b410-8823a20eed82
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e922cd2526002306928b2eae3418185986ed741
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="transmitter-interfaces"></a><span data-ttu-id="f8e6b-102">发射器接口</span><span class="sxs-lookup"><span data-stu-id="f8e6b-102">Transmitter Interfaces</span></span>
<span data-ttu-id="f8e6b-103">除了强制适配器接口，传输 （发送） 适配器，需要实现**IBTTransmitter**它们是否非批处理或**IBTBatchTransmitter**如果按批处理。</span><span class="sxs-lookup"><span data-stu-id="f8e6b-103">In addition to the mandatory adapter interfaces, transmit (send) adapters, need to implement either **IBTTransmitter** if they are non-batched or **IBTBatchTransmitter** if they are batched.</span></span>  
  
 <span data-ttu-id="f8e6b-104">下图显示了按批处理和不按批处理的发送适配器都需要实现的接口。</span><span class="sxs-lookup"><span data-stu-id="f8e6b-104">The following figure shows the interfaces that batched and non-batched send adapters need to implement.</span></span>  
  
 ![](../core/media/transmitterinterfaces.gif "TransmitterInterfaces")