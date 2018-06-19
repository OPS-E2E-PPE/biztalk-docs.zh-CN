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
# <a name="messaging-engine-interfaces"></a><span data-ttu-id="c2d49-102">消息传递引擎接口</span><span class="sxs-lookup"><span data-stu-id="c2d49-102">Messaging Engine Interfaces</span></span>
<span data-ttu-id="c2d49-103">适配器可以使用三种公共接口来允许与消息引擎的交互。</span><span class="sxs-lookup"><span data-stu-id="c2d49-103">There are three public interfaces that adapters can use to allow interaction with the Messaging Engine.</span></span> <span data-ttu-id="c2d49-104">下面几部分将概要介绍这些公共接口。</span><span class="sxs-lookup"><span data-stu-id="c2d49-104">These are outlined in the following sections.</span></span>  
  
## <a name="ibttransportproxy"></a><span data-ttu-id="c2d49-105">IBTTransportProxy</span><span class="sxs-lookup"><span data-stu-id="c2d49-105">IBTTransportProxy</span></span>  
 <span data-ttu-id="c2d49-106">适配器始终通过使用自己的传输代理与消息引擎交互。</span><span class="sxs-lookup"><span data-stu-id="c2d49-106">Adapters always interact with the Messaging Engine by using their own transport proxy.</span></span> <span data-ttu-id="c2d49-107">该传输代理用于创建批、获取消息工厂和向引擎注册独立接收器等操作。</span><span class="sxs-lookup"><span data-stu-id="c2d49-107">The transport proxy is used for operations such as creating batches, getting the message factory, and registering isolated receivers with the engine.</span></span>  
  
## <a name="ibttransportbatch"></a><span data-ttu-id="c2d49-108">IBTTransportBatch</span><span class="sxs-lookup"><span data-stu-id="c2d49-108">IBTTransportBatch</span></span>  
 <span data-ttu-id="c2d49-109">此接口由消息引擎提供，用于定义适配器可用来操作消息批的方法。</span><span class="sxs-lookup"><span data-stu-id="c2d49-109">This interface is provided by the Messaging Engine, and defines methods that adapters can use to operate on batches of messages.</span></span> <span data-ttu-id="c2d49-110">消息引擎通过异步方式处理批。</span><span class="sxs-lookup"><span data-stu-id="c2d49-110">The Messaging Engine processes batches asynchronously.</span></span>  
  
## <a name="ibtdtccommitconfirm"></a><span data-ttu-id="c2d49-111">IBTDTCCommitConfirm</span><span class="sxs-lookup"><span data-stu-id="c2d49-111">IBTDTCCommitConfirm</span></span>  
 <span data-ttu-id="c2d49-112">在批上使用显式 Microsoft 分布式事务处理协调器 (MSDTC) 事务的适配器必须使用此接口来通知引擎该事务的结果。</span><span class="sxs-lookup"><span data-stu-id="c2d49-112">Adapters using explicit Microsoft Distributed Transaction Coordinator (MSDTC) transactions on batches must use this interface to notify the engine of the outcome of the transaction using this interface.</span></span>