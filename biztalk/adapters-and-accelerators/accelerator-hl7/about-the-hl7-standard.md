---
title: 有关 HL7 标准 |Microsoft 文档
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
ms.openlocfilehash: 9185248b5b897fbc7c909786c419b07fc3fb9d61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204837"
---
# <a name="about-the-hl7-standard"></a><span data-ttu-id="20f70-102">有关 HL7 标准</span><span class="sxs-lookup"><span data-stu-id="20f70-102">About the HL7 Standard</span></span>
<span data-ttu-id="20f70-103">运行状况级别七个 (HL7) 标准的目的是便于卫生保健的环境中的通信。</span><span class="sxs-lookup"><span data-stu-id="20f70-103">The purpose of the Health Level Seven (HL7) standard is to facilitate communication in health care environments.</span></span> <span data-ttu-id="20f70-104">主要目的是提供标准间卫生保健的计算机应用程序消除或大幅减少，否则是所必需的自定义接口编程和程序维护的数据交换。</span><span class="sxs-lookup"><span data-stu-id="20f70-104">The primary goal is to provide standards for the exchange of data among health care computer applications that eliminate or substantially reduce the custom interface programming and program maintenance that may otherwise be required.</span></span> <span data-ttu-id="20f70-105">你可以为目标的一组描述此主目标：</span><span class="sxs-lookup"><span data-stu-id="20f70-105">You can delineate this primary goal as a set of goals:</span></span>  
  
-   <span data-ttu-id="20f70-106">标准支持在各种技术的环境中实现的系统之间的交换。</span><span class="sxs-lookup"><span data-stu-id="20f70-106">That the standard supports exchanges among systems implemented in the widest variety of technical environments.</span></span> <span data-ttu-id="20f70-107">其实现应实际在各种编程语言和操作系统。</span><span class="sxs-lookup"><span data-stu-id="20f70-107">Its implementation should be practical in a wide variety of programming languages and operating systems.</span></span> <span data-ttu-id="20f70-108">它还应在各种通信环境中，从完整、 支持通信 OSI 符合，七个级别网络到不太完整的环境，包括基元点对点 RS 232 C"堆栈"互连和传输通过批处理媒体，如软盘磁盘和磁带的数据。</span><span class="sxs-lookup"><span data-stu-id="20f70-108">It should also support communications in a wide variety of communications environments, ranging from a full, OSI-compliant, seven level network "stack" to less complete environments, including primitive point-to-point RS 232C interconnections and transfer of data by batch media, such as floppy disk and tape.</span></span>  
  
-   <span data-ttu-id="20f70-109">标准支持文件传输以及多个事务的单个事务的即时的传输。</span><span class="sxs-lookup"><span data-stu-id="20f70-109">That the standard supports immediate transfer of single transactions along with file transfers of multiple transactions.</span></span>  
  
-   <span data-ttu-id="20f70-110">标准来实现最大的可能程度的标准化，与网站使用情况和的某些数据元素的格式的变体一致。</span><span class="sxs-lookup"><span data-stu-id="20f70-110">That the standard achieves the greatest possible degree of standardization, consistent with site variations in the usage and format of certain data elements.</span></span> <span data-ttu-id="20f70-111">标准应容纳需要特定于站点的变体。</span><span class="sxs-lookup"><span data-stu-id="20f70-111">The standard should accommodate necessary site-specific variations.</span></span> <span data-ttu-id="20f70-112">至少，这将包括特定于站点的表、 代码定义和可能是特定于站点的消息段 （例如，HL7 Z 段）。</span><span class="sxs-lookup"><span data-stu-id="20f70-112">This will include, at least, site-specific tables, code definitions, and possibly site-specific message segments (for example, HL7 Z segments).</span></span>  
  
-   <span data-ttu-id="20f70-113">标准必须支持演化增长识别新的要求。</span><span class="sxs-lookup"><span data-stu-id="20f70-113">That the standard must support evolutionary growth as new requirements are recognized.</span></span> <span data-ttu-id="20f70-114">这包括支持的扩展和新版本引入现有的操作环境的过程。</span><span class="sxs-lookup"><span data-stu-id="20f70-114">This includes support of the process of introducing extensions and new releases into existing operational environments.</span></span>  
  
-   <span data-ttu-id="20f70-115">使用现有的生产协议和接受的行业标准协议，HL7 组织应基于标准体验。</span><span class="sxs-lookup"><span data-stu-id="20f70-115">That the HL7 organization should base the standard on experiences with existing production protocols and accepted industry-wide standard protocols.</span></span> <span data-ttu-id="20f70-116">但是，标准应该不倾向于特定的公司，从而对其他用户的标准不利的专有兴趣。</span><span class="sxs-lookup"><span data-stu-id="20f70-116">However, the standard should not favor the proprietary interests of specific companies to the detriment of other users of the standard.</span></span> <span data-ttu-id="20f70-117">同时，HL7 寻求保留单独的供应商可以将设置到应用商店的唯一属性。</span><span class="sxs-lookup"><span data-stu-id="20f70-117">At the same time, HL7 seeks to preserve the unique attributes that an individual vendor can bring to the marketplace.</span></span>  
  
-   <span data-ttu-id="20f70-118">虽然很有用且相关以专注于信息系统中医院，标准的长期目标应在所有卫生保健的环境中定义的格式和计算机应用程序的协议。</span><span class="sxs-lookup"><span data-stu-id="20f70-118">While it is both useful and pertinent to focus on information systems within hospitals, the long-term goal of the standard should be to define formats and protocols for computer applications in all health care environments.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20f70-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="20f70-119">In This Section</span></span>  
  
-   [<span data-ttu-id="20f70-120">HL7 版本</span><span class="sxs-lookup"><span data-stu-id="20f70-120">HL7 Versions</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-versions.md)