---
title: 批处理疑难解答 |Microsoft Docs
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
ms.openlocfilehash: de82fb536dcd23410b485a12eccba1592ccebbe2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286504"
---
# <a name="troubleshooting-batching"></a><span data-ttu-id="d0aaf-102">批处理疑难解答</span><span class="sxs-lookup"><span data-stu-id="d0aaf-102">Troubleshooting Batching</span></span>
<span data-ttu-id="d0aaf-103">解决了与相关的问题[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]批处理。</span><span class="sxs-lookup"><span data-stu-id="d0aaf-103">Addresses issues related to [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] batching.</span></span>  
  
## <a name="error-activating-batch"></a><span data-ttu-id="d0aaf-104">错误激活批处理</span><span class="sxs-lookup"><span data-stu-id="d0aaf-104">Error activating batch</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="d0aaf-105">故障现象</span><span class="sxs-lookup"><span data-stu-id="d0aaf-105">Symptom</span></span>  
 <span data-ttu-id="d0aaf-106">无法激活批处理。</span><span class="sxs-lookup"><span data-stu-id="d0aaf-106">Unable to activate a batch.</span></span> <span data-ttu-id="d0aaf-107">您收到常规网络错误。</span><span class="sxs-lookup"><span data-stu-id="d0aaf-107">You get a general network error.</span></span>  
  
<span data-ttu-id="d0aaf-108">**可能的原因**:[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]重新启动，但[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器不是。</span><span class="sxs-lookup"><span data-stu-id="d0aaf-108">**Possible Cause** : [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] was restarted, but [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer was not.</span></span>  
  
<span data-ttu-id="d0aaf-109">**解析**:重新启动[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="d0aaf-109">**Resolution** : Restart [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
## <a name="messages-are-not-batched-when-the-target-namespace-is-not-the-default"></a><span data-ttu-id="d0aaf-110">消息不进行批处理时的目标命名空间不是默认值</span><span class="sxs-lookup"><span data-stu-id="d0aaf-110">Messages are not batched when the target namespace is not the default</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="d0aaf-111">故障现象</span><span class="sxs-lookup"><span data-stu-id="d0aaf-111">Symptom</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="d0aaf-112">未对消息进行批处理。</span><span class="sxs-lookup"><span data-stu-id="d0aaf-112">is not batching messages.</span></span>  
  
<span data-ttu-id="d0aaf-113">**可能的原因**:源和目标参与方不是同一架构命名空间中。</span><span class="sxs-lookup"><span data-stu-id="d0aaf-113">**Possible Cause** : Source and destination parties are not in the same schema namespace.</span></span>  
  
<span data-ttu-id="d0aaf-114">**解析**:如果需要验证源和目标参与方必须使用相同的架构命名空间。</span><span class="sxs-lookup"><span data-stu-id="d0aaf-114">**Resolution** : Source and destination parties must use the same schema namespace if validation is required.</span></span> <span data-ttu-id="d0aaf-115">请确保源和目标参与方都使用相同的架构命名空间。</span><span class="sxs-lookup"><span data-stu-id="d0aaf-115">Ensure the source and destination parties are using the same schema namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0aaf-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0aaf-116">See Also</span></span>  
 [<span data-ttu-id="d0aaf-117">HL7 的疑难解答和已知问题</span><span class="sxs-lookup"><span data-stu-id="d0aaf-117">Troubleshooting and known issues in HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)