---
title: "使用 Microsoft BizTalk LoadGen 2007 工具 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- LoadGen tool, how to
- LoadGen tool, test environments
ms.assetid: d1973a26-1c98-4261-bd9a-6357cdb19ccf
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b93018f093bbdffed64c44060f445a30d37344c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-microsoft-biztalk-loadgen-2007-tool"></a>使用 Microsoft BizTalk LoadGen 2007 工具
Microsoft BizTalk LoadGen 2007 工具可供开发人员和 IT 专家模拟 BizTalk Server 上的负载。 使用此工具，可以模拟负载，以便根据 BizTalk 部署检测性能和压力。 此外，开发人员还可以扩展此工具，以便模拟自定义传输的负载。  
  
> [!NOTE]
>  LoadGen 2007 工具是可在下载[http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841)。 此工具的以前版本，BizTalk Server 2004 负载生成工具是可在下载[http://go.microsoft.com/fwlink/?LinkId=108999](http://go.microsoft.com/fwlink/?LinkId=108999)。  
  
 此工具应仅用于测试环境中，不应用于生产环境中。 此工具以“保持原样”提供，不支持用于生产环境中。  
  
> [!NOTE]
>  您可以结合使用 BizTalk Server 2004 负载生成工具和 MSMQ 适配器，但必须进行一些额外操作。 有关说明，请参阅[使用 MSMQ LoadGen 2007](../core/using-loadgen-2007-with-msmq.md)。  
  
> [!NOTE]
>  64 位计算机上不支持使用 LoadGen 功能。 您可以远程使用运行在 32 位计算机上的 LoadGen 以生成对 64 位服务器的负载。  
  
## <a name="see-also"></a>另请参阅  
 [Overdrive 负载测试](../core/overdrive-load-test.md)