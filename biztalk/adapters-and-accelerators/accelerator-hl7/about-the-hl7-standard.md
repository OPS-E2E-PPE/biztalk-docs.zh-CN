---
title: 关于 HL7 标准 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- standards [HL7]
- HL7, standards
- Health Level Seven (HL7)
ms.assetid: 15f26ae3-d1ad-40a4-aafe-7148ef30cadb
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34234723c05ac14c6e7964ce23ee1ef394760796
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244447"
---
# <a name="about-the-hl7-standard"></a><span data-ttu-id="8549c-102">关于 HL7 标准</span><span class="sxs-lookup"><span data-stu-id="8549c-102">About the HL7 Standard</span></span>
<span data-ttu-id="8549c-103">运行状况级别 7 (HL7) 标准的目的是便于卫生保健的环境中的通信。</span><span class="sxs-lookup"><span data-stu-id="8549c-103">The purpose of the Health Level Seven (HL7) standard is to facilitate communication in health care environments.</span></span> <span data-ttu-id="8549c-104">主要目的是消除或大幅降低可能是必需的自定义接口编程和程序维护的卫生保健计算机应用程序间的数据交换提供标准。</span><span class="sxs-lookup"><span data-stu-id="8549c-104">The primary goal is to provide standards for the exchange of data among health care computer applications that eliminate or substantially reduce the custom interface programming and program maintenance that may otherwise be required.</span></span> <span data-ttu-id="8549c-105">您可以为一组的目标描绘此主目标：</span><span class="sxs-lookup"><span data-stu-id="8549c-105">You can delineate this primary goal as a set of goals:</span></span>  
  
-   <span data-ttu-id="8549c-106">Standard 支持在各种技术环境中实现的系统之间交换。</span><span class="sxs-lookup"><span data-stu-id="8549c-106">That the standard supports exchanges among systems implemented in the widest variety of technical environments.</span></span> <span data-ttu-id="8549c-107">其实现应该是适合在各种编程语言和操作系统。</span><span class="sxs-lookup"><span data-stu-id="8549c-107">Its implementation should be practical in a wide variety of programming languages and operating systems.</span></span> <span data-ttu-id="8549c-108">它还应通过以下方式支持通信中各种通信环境，从完整、 OSI 符合，七个级别网络到不太完整的环境，包括基元点对点 RS 232 C"堆栈"互连和传输通过批处理媒体，如软盘磁盘和磁带的数据。</span><span class="sxs-lookup"><span data-stu-id="8549c-108">It should also support communications in a wide variety of communications environments, ranging from a full, OSI-compliant, seven level network "stack" to less complete environments, including primitive point-to-point RS 232C interconnections and transfer of data by batch media, such as floppy disk and tape.</span></span>  
  
-   <span data-ttu-id="8549c-109">标准支持单一事务以及文件传输的多个事务的即时的传输。</span><span class="sxs-lookup"><span data-stu-id="8549c-109">That the standard supports immediate transfer of single transactions along with file transfers of multiple transactions.</span></span>  
  
-   <span data-ttu-id="8549c-110">标准，从而实现最大的可能程度的标准化，与站点中的使用情况和某些数据元素的格式的变体保持一致。</span><span class="sxs-lookup"><span data-stu-id="8549c-110">That the standard achieves the greatest possible degree of standardization, consistent with site variations in the usage and format of certain data elements.</span></span> <span data-ttu-id="8549c-111">标准应满足必要的特定于站点变体。</span><span class="sxs-lookup"><span data-stu-id="8549c-111">The standard should accommodate necessary site-specific variations.</span></span> <span data-ttu-id="8549c-112">至少，这将包括特定于站点的表、 代码定义和可能是特定于站点的消息段 （例如，HL7 的 Z 段）。</span><span class="sxs-lookup"><span data-stu-id="8549c-112">This will include, at least, site-specific tables, code definitions, and possibly site-specific message segments (for example, HL7 Z segments).</span></span>  
  
-   <span data-ttu-id="8549c-113">标准必须支持进化的增长，因为识别新的要求。</span><span class="sxs-lookup"><span data-stu-id="8549c-113">That the standard must support evolutionary growth as new requirements are recognized.</span></span> <span data-ttu-id="8549c-114">这包括引入到现有的运行环境的扩展和新版本的过程的支持。</span><span class="sxs-lookup"><span data-stu-id="8549c-114">This includes support of the process of introducing extensions and new releases into existing operational environments.</span></span>  
  
-   <span data-ttu-id="8549c-115">HL7 组织应使标准，基于体验与现有生产协议和接受的行业级标准协议。</span><span class="sxs-lookup"><span data-stu-id="8549c-115">That the HL7 organization should base the standard on experiences with existing production protocols and accepted industry-wide standard protocols.</span></span> <span data-ttu-id="8549c-116">但是，标准应支持专有感兴趣的特定公司标准的其他用户，从而不利。</span><span class="sxs-lookup"><span data-stu-id="8549c-116">However, the standard should not favor the proprietary interests of specific companies to the detriment of other users of the standard.</span></span> <span data-ttu-id="8549c-117">同时，HL7 设法保留各个供应商可以为市场带来的唯一属性。</span><span class="sxs-lookup"><span data-stu-id="8549c-117">At the same time, HL7 seeks to preserve the unique attributes that an individual vendor can bring to the marketplace.</span></span>  
  
-   <span data-ttu-id="8549c-118">尽管非常有用且相关，可以将精力集中在医院中的信息系统上，但应该是标准的长期目标卫生保健的所有环境中定义的格式和计算机应用程序的协议。</span><span class="sxs-lookup"><span data-stu-id="8549c-118">While it is both useful and pertinent to focus on information systems within hospitals, the long-term goal of the standard should be to define formats and protocols for computer applications in all health care environments.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8549c-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="8549c-119">In This Section</span></span>  
  
-   [<span data-ttu-id="8549c-120">HL7 版本</span><span class="sxs-lookup"><span data-stu-id="8549c-120">HL7 Versions</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-versions.md)