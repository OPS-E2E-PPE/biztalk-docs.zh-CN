---
title: 适配器接口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7398aeb-7c1c-400e-a552-d0ab39e55a0b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bdb6f3e26d8862fd538f0279ecbb4c5c9b33af8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361405"
---
# <a name="adapter-interfaces"></a><span data-ttu-id="c056e-102">适配器接口</span><span class="sxs-lookup"><span data-stu-id="c056e-102">Adapter Interfaces</span></span>
<span data-ttu-id="c056e-103">有三个必须实现自定义适配器的接口和两个接口是可选的。</span><span class="sxs-lookup"><span data-stu-id="c056e-103">There are three interfaces that custom adapters must implement, and two interfaces that are optional.</span></span>  
  
## <a name="mandatory-interfaces"></a><span data-ttu-id="c056e-104">必需接口</span><span class="sxs-lookup"><span data-stu-id="c056e-104">Mandatory interfaces</span></span>  
 <span data-ttu-id="c056e-105">所有适配器必须都实现以下接口。</span><span class="sxs-lookup"><span data-stu-id="c056e-105">All adapters must implement the following interfaces.</span></span>  
  
### <a name="ibasecomponent"></a><span data-ttu-id="c056e-106">IBaseComponent</span><span class="sxs-lookup"><span data-stu-id="c056e-106">IBaseComponent</span></span>  
 <span data-ttu-id="c056e-107">此接口用于详细**名称**，**版本**，并**说明**的适配器。</span><span class="sxs-lookup"><span data-stu-id="c056e-107">This interface details the **Name**, **Version**, and **Description** of the adapter.</span></span>  
  
### <a name="ibttransport"></a><span data-ttu-id="c056e-108">IBTTransport</span><span class="sxs-lookup"><span data-stu-id="c056e-108">IBTTransport</span></span>  
 <span data-ttu-id="c056e-109">此接口用于详细**传输类型**并**ClassID**的适配器。</span><span class="sxs-lookup"><span data-stu-id="c056e-109">This interface details the **Transport Type** and **ClassID** of the adapter.</span></span>  
  
### <a name="ibtbatchcallback"></a><span data-ttu-id="c056e-110">IBTBatchCallback</span><span class="sxs-lookup"><span data-stu-id="c056e-110">IBTBatchCallback</span></span>  
 <span data-ttu-id="c056e-111">此接口是通过该适配器接收的状态和错误信息一批消息提交给消息引擎的回调接口。</span><span class="sxs-lookup"><span data-stu-id="c056e-111">This interface is a callback interface through which the adapter receives status and error information for a batch of messages it submits to the Messaging Engine.</span></span>  
  
## <a name="optional-interfaces"></a><span data-ttu-id="c056e-112">可选接口</span><span class="sxs-lookup"><span data-stu-id="c056e-112">Optional interfaces</span></span>  
 <span data-ttu-id="c056e-113">适配器可能会或可能不会实现以下接口，具体取决于他们的需要。</span><span class="sxs-lookup"><span data-stu-id="c056e-113">Adapters may or may not implement the following interfaces, depending on their needs.</span></span>  
  
### <a name="ipersistpropertybag"></a><span data-ttu-id="c056e-114">IPersistPropertyBag</span><span class="sxs-lookup"><span data-stu-id="c056e-114">IPersistPropertyBag</span></span>  
 <span data-ttu-id="c056e-115">这是通过哪个处理程序配置传送到适配器配置接口。</span><span class="sxs-lookup"><span data-stu-id="c056e-115">This is a configuration interface through which handler configuration is delivered to the adapter.</span></span> <span data-ttu-id="c056e-116">仅适用于具有处理程序配置信息的适配器需要此接口。</span><span class="sxs-lookup"><span data-stu-id="c056e-116">This interface is required only for adapters that have handler configuration information.</span></span>  
  
### <a name="ibttransportcontrol"></a><span data-ttu-id="c056e-117">IBTTransportControl</span><span class="sxs-lookup"><span data-stu-id="c056e-117">IBTTransportControl</span></span>  
 <span data-ttu-id="c056e-118">此接口用于初始化和终止适配器。</span><span class="sxs-lookup"><span data-stu-id="c056e-118">This interface is used to initialize and terminate an adapter.</span></span> <span data-ttu-id="c056e-119">适配器的传输代理是通过此接口传递给它。</span><span class="sxs-lookup"><span data-stu-id="c056e-119">The adapter's transport proxy is passed to it through this interface.</span></span> <span data-ttu-id="c056e-120">此接口不需要独立适配器。</span><span class="sxs-lookup"><span data-stu-id="c056e-120">This interface is not required for isolated adapters.</span></span>