---
title: 检测的高性能 BizTalk 解决方案的最佳实践 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd16ea1e-055a-429b-912f-bff2b91f0fdb
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ef6f243f894071aebb0089f063ed0242ee09d9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298517"
---
# <a name="instrumentation-best-practices-for-high-performance-biztalk-solutions"></a>检测的高性能 BizTalk 解决方案的最佳实践
若要下载本白皮书的副本，请转到[http://go.microsoft.com/fwlink/?LinkId=205874](http://go.microsoft.com/fwlink/?LinkId=205874)。  
  
 **发布日期：** 2010 年 11 月  
  
 **作者：** Valery Mizonov、 Microsoft Corporation  
  
 **审阅者：**  
  
-   Mark Simms、 Microsoft Corporation  
  
-   Jayanthi Sampathkumar，Microsoft Corporation  
  
-   Krish Srinivasan，Microsoft Corporation  
  
 **适用于：** Microsoft BizTalk Server  
  
 **摘要：** 检测 BizTalk 解决方案的传统方法可能不是始终都从性能角度来看最有效。 常用的检测和跟踪组件利用 Win32 调试 Api 可能介绍潜在瓶颈，并可负责压力下运行的多线程 BizTalk 应用程序中的性能下降。  
  
 从另一侧，源代码检测提供更大程度的可见性的应用程序行为，并有助于降低总体故障排除工作。 因此，一种全新到检测的高性能 BizTalk 解决方案变得至关重要的一点是重要，以启用与几乎无开销并且不会影响非侵入性的方式收集的丰富且详细的诊断信息上的应用程序性能。  
  
 [Windows Server AppFabric 客户咨询团队](http://blogs.msdn.com/appfabriccat)microsoft 旨在提供社区的经验证的最佳做法，以帮助 BizTalk 开发人员扩充其解决方案的高性能检测内部采用由许多 Microsoft 产品。 这些最佳做法使在一个可重用的框架，它 BizTalk 开发人员可以轻松插入和采用其自己的实现中的窗体中反映出来。  
  
 你可以下载的完整副本[检测的高性能 BizTalk 解决方案的最佳实践](http://go.microsoft.com/fwlink/?LinkId=205874)(http://go.microsoft.com/fwlink/?LinkId=205874) 在 Microsoft 下载中心上。