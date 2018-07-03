---
title: 高性能 BizTalk 解决方案的检测最佳做法 |Microsoft Docs
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
ms.openlocfilehash: 60faad9e9e2905da963ee911dc9d7f13a39d2c67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997462"
---
# <a name="instrumentation-best-practices-for-high-performance-biztalk-solutions"></a>高性能 BizTalk 解决方案的检测最佳做法
若要下载本白皮书的副本，请转到[ http://go.microsoft.com/fwlink/?LinkId=205874 ](http://go.microsoft.com/fwlink/?LinkId=205874)。  
  
 **发布日期：** 2010 年 11 月  
  
 **作者：** Valery Mizonov、 Microsoft Corporation  
  
 **审阅者：**  
  
- Mark Simms、 Microsoft Corporation  
  
- Jayanthi Sampathkumar，Microsoft Corporation  
  
- Krish Srinivasan，Microsoft Corporation  
  
  **适用于：** Microsoft BizTalk Server  
  
  **摘要：** 检测 BizTalk 解决方案的传统方法可能始终无法从性能角度来看最有效。 常用的检测和跟踪组件利用 Win32 调试 Api 可能会造成潜在瓶颈并让其负责在压力下运行的多线程 BizTalk 应用程序中的性能下降。  
  
  从另一侧，源代码检测提供非常精确地洞察应用程序的行为，并有助于降低整体故障排除工作。 因此，一种全新检测的高性能 BizTalk 解决方案变得至关重要的一点是重要，以便使用几乎没有开销也不会影响非侵入性的方式收集诊断信息丰富和详细信息对应用程序性能。  
  
  [Windows Server AppFabric 客户顾问团队](http://blogs.msdn.com/appfabriccat)microsoft 旨在为社区提供经过验证的最佳实践可帮助扩充其解决方案的高性能检测与 BizTalk 开发人员在内部采用由许多 Microsoft 产品。 一个可重复使用的框架，BizTalk 开发人员可以轻松地插入，在他们自己的实现中采用的形式有尚未反映这些最佳实践。  
  
  您可以下载的完整副本[高性能 BizTalk 解决方案的检测最佳做法](http://go.microsoft.com/fwlink/?LinkId=205874)(http://go.microsoft.com/fwlink/?LinkId=205874)从 Microsoft 下载中心获得。