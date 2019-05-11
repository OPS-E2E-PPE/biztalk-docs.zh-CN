---
title: 使用 POP3 适配器的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6d621a2-4801-44fe-a266-d4c05ac82633
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78e978ed5be5fa556411566d35aa6fcf58c09fec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380737"
---
# <a name="known-issues-with-the-pop3-adapter"></a><span data-ttu-id="ca30b-102">POP3 适配器已知问题</span><span class="sxs-lookup"><span data-stu-id="ca30b-102">Known Issues with the POP3 Adapter</span></span>
<span data-ttu-id="ca30b-103">本部分包含可能帮助您避免错误的信息。</span><span class="sxs-lookup"><span data-stu-id="ca30b-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="ca30b-104">已知问题</span><span class="sxs-lookup"><span data-stu-id="ca30b-104">Known Issues</span></span>  
  
#### <a name="the-pop3-adapter-fails-to-process-documents-when-running-on-a-64-bit-operating-system"></a><span data-ttu-id="ca30b-105">POP3 适配器无法处理文档，在 64 位操作系统上运行时</span><span class="sxs-lookup"><span data-stu-id="ca30b-105">The POP3 Adapter fails to process documents when running on a 64 bit operating system</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="ca30b-106">问题</span><span class="sxs-lookup"><span data-stu-id="ca30b-106">Problem</span></span>  
 <span data-ttu-id="ca30b-107">在 64 位操作系统上运行时，POP3 适配器将不处理文档。</span><span class="sxs-lookup"><span data-stu-id="ca30b-107">The POP3 Adapter will not process documents when running on a 64 bit operating system.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="ca30b-108">原因</span><span class="sxs-lookup"><span data-stu-id="ca30b-108">Cause</span></span>  
 <span data-ttu-id="ca30b-109">POP3 适配器的适配器处理程序无法在 64 位主机实例中运行。</span><span class="sxs-lookup"><span data-stu-id="ca30b-109">The POP3 Adapter adapter handler is unable to run in a 64 bit host instance.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="ca30b-110">解决方法</span><span class="sxs-lookup"><span data-stu-id="ca30b-110">Resolution</span></span>  
 <span data-ttu-id="ca30b-111">如果在 64 位计算机上正在运行 POP3 适配器，配置 POP3 适配器处理程序，在 32 位主机中运行。</span><span class="sxs-lookup"><span data-stu-id="ca30b-111">If you are running the POP3 Adapter on a 64 bit machine, configure the POP3 Adapter handlers to run in a 32 bit host.</span></span> <span data-ttu-id="ca30b-112">此选项才可从 BizTalk 管理控制台访问的主机属性页上可用。</span><span class="sxs-lookup"><span data-stu-id="ca30b-112">This option is available on the Host Properties page accessible from the BizTalk Administration console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca30b-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca30b-113">See Also</span></span>  
 [<span data-ttu-id="ca30b-114">POP3 适配器故障排除</span><span class="sxs-lookup"><span data-stu-id="ca30b-114">Troubleshooting the POP3 Adapter</span></span>](../core/troubleshooting-the-pop3-adapter.md)