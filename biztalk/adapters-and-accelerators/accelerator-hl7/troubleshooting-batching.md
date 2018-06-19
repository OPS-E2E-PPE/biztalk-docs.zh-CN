---
title: 故障排除批处理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, troubleshooting
- troubleshooting, batching
ms.assetid: f47e1a16-47fd-4bd8-8dad-fcdba31a833e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94c8413a8022529e6ace56c50d5e6d75267a72e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206301"
---
# <a name="troubleshooting-batching"></a><span data-ttu-id="211c5-102">故障排除批处理</span><span class="sxs-lookup"><span data-stu-id="211c5-102">Troubleshooting Batching</span></span>
<span data-ttu-id="211c5-103">解决与相关的问题，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]批处理。</span><span class="sxs-lookup"><span data-stu-id="211c5-103">Addresses issues related to [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] batching.</span></span>  
  
## <a name="error-activating-batch"></a><span data-ttu-id="211c5-104">错误激活批处理</span><span class="sxs-lookup"><span data-stu-id="211c5-104">Error activating batch</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="211c5-105">故障现象</span><span class="sxs-lookup"><span data-stu-id="211c5-105">Symptom</span></span>  
 <span data-ttu-id="211c5-106">无法激活一批。</span><span class="sxs-lookup"><span data-stu-id="211c5-106">Unable to activate a batch.</span></span> <span data-ttu-id="211c5-107">获取一般网络错误。</span><span class="sxs-lookup"><span data-stu-id="211c5-107">You get a general network error.</span></span>  
  
<span data-ttu-id="211c5-108">**可能的原因**:[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]已重新启动，但[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器不是。</span><span class="sxs-lookup"><span data-stu-id="211c5-108">**Possible Cause** : [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] was restarted, but [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer was not.</span></span>  
  
<span data-ttu-id="211c5-109">**解析**： 重新启动[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="211c5-109">**Resolution** : Restart [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
## <a name="messages-are-not-batched-when-the-target-namespace-is-not-the-default"></a><span data-ttu-id="211c5-110">批处理消息一次不时的目标命名空间不是默认值</span><span class="sxs-lookup"><span data-stu-id="211c5-110">Messages are not batched when the target namespace is not the default</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="211c5-111">故障现象</span><span class="sxs-lookup"><span data-stu-id="211c5-111">Symptom</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="211c5-112">未对消息进行批处理。</span><span class="sxs-lookup"><span data-stu-id="211c5-112"> is not batching messages.</span></span>  
  
<span data-ttu-id="211c5-113">**可能的原因**： 源和目标方不在相同的架构命名空间。</span><span class="sxs-lookup"><span data-stu-id="211c5-113">**Possible Cause** : Source and destination parties are not in the same schema namespace.</span></span>  
  
<span data-ttu-id="211c5-114">**解析**： 源和目标方必须使用相同的架构命名空间，如果需要验证。</span><span class="sxs-lookup"><span data-stu-id="211c5-114">**Resolution** : Source and destination parties must use the same schema namespace if validation is required.</span></span> <span data-ttu-id="211c5-115">请确保源和目标方使用相同的架构命名空间。</span><span class="sxs-lookup"><span data-stu-id="211c5-115">Ensure the source and destination parties are using the same schema namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="211c5-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="211c5-116">See Also</span></span>  
 [<span data-ttu-id="211c5-117">在 HL7 疑难解答和已知问题</span><span class="sxs-lookup"><span data-stu-id="211c5-117">Troubleshooting and known issues in HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)