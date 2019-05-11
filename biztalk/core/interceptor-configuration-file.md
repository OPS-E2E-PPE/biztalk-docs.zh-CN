---
title: 侦听器配置文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 490f5607-e7f6-4f7f-9121-1070db32a7cf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4af3c9b91d7f8d5dc58cb40f4cb8d3a1f66dc657
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382044"
---
# <a name="interceptor-configuration-file"></a><span data-ttu-id="7928f-102">侦听器配置文件</span><span class="sxs-lookup"><span data-stu-id="7928f-102">Interceptor Configuration File</span></span>
<span data-ttu-id="7928f-103">用于 Windows Workflow Foundation 和 Windows Communication Foundation 的 BAM 侦听器依赖于侦听器配置文件来确定要侦听的事件和日期元素。</span><span class="sxs-lookup"><span data-stu-id="7928f-103">The BAM interceptors for Windows Workflow Foundation and Windows Communication Foundation rely on an interceptor configuration file to determine what events and date elements to intercept.</span></span> <span data-ttu-id="7928f-104">配置文件为 XML 文件并由侦听器配置架构和 Windows Workflow Foundation 架构或 Windows Communication Framework 架构（具体取决于所针对的技术）定义。</span><span class="sxs-lookup"><span data-stu-id="7928f-104">The configuration file is XML and is defined by the interceptor configuration schema and either the Windows Workflow Foundation schema or the Windows Communication Framework schema depending upon which technology you are targeting.</span></span>  
  
 <span data-ttu-id="7928f-105">本部分着重介绍包括元素和属性在内的基本侦听器配置。</span><span class="sxs-lookup"><span data-stu-id="7928f-105">This section focuses on the base interceptor configuration including elements and attributes.</span></span> <span data-ttu-id="7928f-106">其他功能由特定于技术的侦听器提供并在单独章节中介绍。</span><span class="sxs-lookup"><span data-stu-id="7928f-106">Additional functionality is provided by the technology-specific interceptors and are explained in separate sections.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7928f-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="7928f-107">In This Section</span></span>  
  
-   [<span data-ttu-id="7928f-108">使用 IntelliSense 创建侦听器配置文件</span><span class="sxs-lookup"><span data-stu-id="7928f-108">Using IntelliSense to Create an Interceptor Configuration File</span></span>](../core/using-intellisense-to-create-an-interceptor-configuration-file.md)  
  
-   [<span data-ttu-id="7928f-109">侦听器配置架构</span><span class="sxs-lookup"><span data-stu-id="7928f-109">Interceptor Configuration Schema</span></span>](../core/interceptor-configuration-schema.md)  
  
-   [<span data-ttu-id="7928f-110">侦听器配置文件的结构</span><span class="sxs-lookup"><span data-stu-id="7928f-110">Structure of an Interceptor Configuration File</span></span>](../core/structure-of-an-interceptor-configuration-file.md)  
  
## <a name="see-also"></a><span data-ttu-id="7928f-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="7928f-111">See Also</span></span>  
 <span data-ttu-id="7928f-112">[BAM WF Interceptor](../core/bam-wf-interceptor.md) </span><span class="sxs-lookup"><span data-stu-id="7928f-112">[BAM WF Interceptor](../core/bam-wf-interceptor.md) </span></span>  
 [<span data-ttu-id="7928f-113">BAM WCF 侦听器</span><span class="sxs-lookup"><span data-stu-id="7928f-113">BAM WCF Interceptor</span></span>](../core/bam-wcf-interceptor.md)