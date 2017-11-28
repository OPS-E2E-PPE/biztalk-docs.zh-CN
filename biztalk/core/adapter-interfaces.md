---
title: "适配器接口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7398aeb-7c1c-400e-a552-d0ab39e55a0b
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 717adcf5d4a706a7cc072b42b224ab0f9f8cc6fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-interfaces"></a><span data-ttu-id="6def9-102">适配器接口</span><span class="sxs-lookup"><span data-stu-id="6def9-102">Adapter Interfaces</span></span>
<span data-ttu-id="6def9-103">有三个自定义适配器必须实现的接口，另外还有两个可选接口。</span><span class="sxs-lookup"><span data-stu-id="6def9-103">There are three interfaces that custom adapters must implement, and two interfaces that are optional.</span></span>  
  
## <a name="mandatory-interfaces"></a><span data-ttu-id="6def9-104">必需接口</span><span class="sxs-lookup"><span data-stu-id="6def9-104">Mandatory interfaces</span></span>  
 <span data-ttu-id="6def9-105">所有适配器必须实现以下接口。</span><span class="sxs-lookup"><span data-stu-id="6def9-105">All adapters must implement the following interfaces.</span></span>  
  
### <a name="ibasecomponent"></a><span data-ttu-id="6def9-106">IBaseComponent</span><span class="sxs-lookup"><span data-stu-id="6def9-106">IBaseComponent</span></span>  
 <span data-ttu-id="6def9-107">此接口的详细信息**名称**，**版本**，和**说明**的适配器。</span><span class="sxs-lookup"><span data-stu-id="6def9-107">This interface details the **Name**, **Version**, and **Description** of the adapter.</span></span>  
  
### <a name="ibttransport"></a><span data-ttu-id="6def9-108">IBTTransport</span><span class="sxs-lookup"><span data-stu-id="6def9-108">IBTTransport</span></span>  
 <span data-ttu-id="6def9-109">此接口的详细信息**传输类型**和**ClassID**的适配器。</span><span class="sxs-lookup"><span data-stu-id="6def9-109">This interface details the **Transport Type** and **ClassID** of the adapter.</span></span>  
  
### <a name="ibtbatchcallback"></a><span data-ttu-id="6def9-110">IBTBatchCallback</span><span class="sxs-lookup"><span data-stu-id="6def9-110">IBTBatchCallback</span></span>  
 <span data-ttu-id="6def9-111">此接口为回调接口，适配器通过此接口接收其提交给消息引擎的某批消息的状态和错误信息。</span><span class="sxs-lookup"><span data-stu-id="6def9-111">This interface is a callback interface through which the adapter receives status and error information for a batch of messages it submits to the Messaging Engine.</span></span>  
  
## <a name="optional-interfaces"></a><span data-ttu-id="6def9-112">可选接口</span><span class="sxs-lookup"><span data-stu-id="6def9-112">Optional interfaces</span></span>  
 <span data-ttu-id="6def9-113">适配器可以根据其需要实现或不实现以下接口：</span><span class="sxs-lookup"><span data-stu-id="6def9-113">Adapters may or may not implement the following interfaces, depending on their needs.</span></span>  
  
### <a name="ipersistpropertybag"></a><span data-ttu-id="6def9-114">IPersistPropertyBag</span><span class="sxs-lookup"><span data-stu-id="6def9-114">IPersistPropertyBag</span></span>  
 <span data-ttu-id="6def9-115">这是一个配置接口，处理程序配置通过此接口传送给适配器。</span><span class="sxs-lookup"><span data-stu-id="6def9-115">This is a configuration interface through which handler configuration is delivered to the adapter.</span></span> <span data-ttu-id="6def9-116">只有具有处理程序配置信息的适配器才需要此接口。</span><span class="sxs-lookup"><span data-stu-id="6def9-116">This interface is required only for adapters that have handler configuration information.</span></span>  
  
### <a name="ibttransportcontrol"></a><span data-ttu-id="6def9-117">IBTTransportControl</span><span class="sxs-lookup"><span data-stu-id="6def9-117">IBTTransportControl</span></span>  
 <span data-ttu-id="6def9-118">此接口用于初始化和终止适配器。</span><span class="sxs-lookup"><span data-stu-id="6def9-118">This interface is used to initialize and terminate an adapter.</span></span> <span data-ttu-id="6def9-119">适配器的传输代理是通过此接口传递给适配器的。</span><span class="sxs-lookup"><span data-stu-id="6def9-119">The adapter's transport proxy is passed to it through this interface.</span></span> <span data-ttu-id="6def9-120">独立适配器不需要此接口。</span><span class="sxs-lookup"><span data-stu-id="6def9-120">This interface is not required for isolated adapters.</span></span>