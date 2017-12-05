---
title: "如何部署 BizTalk Server 中的程序集 |Microsoft 文档"
description: "将程序集部署到 GAC 中，并启用 BizTalk Server 中的程序集的版本控制"
ms.custom: 
ms.date: 01/21/2016
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7f99ed5-b64a-4a38-99d7-83070fb69030
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb6c787219855ca219808fc1e95c0caefbf12a9d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="biztalk-assemblies"></a>BizTalk 程序集
Microsoft BizTalk Server 和 .NET Framework 最重要的一个方面是：所有 BizTalk Server 项目（映射、架构、业务流程和管道）都已编译到 .NET 程序集中。 此设计的两个最重要含义是：这些程序集必须具有强名称，为此它们还需遵守 .NET 版本控制规则。 其主要含义是：根据特定版本的其他 .NET 项目或程序集（包括 BizTalk 项目）生成 BizTalk 项目后，该 BizTalk 项目将继续使用该版本，直到根据更高的版本重新生成该 BizTalk 项目。  
  
## <a name="net-versioning-and-assemblies"></a>.NET 版本控制和程序集  
 如果在没有停止和启动加载类型的 BizTalk 主机实例的情况下，没有更改 BizTalk 项目上的版本号而重新部署了程序集，则在进行与 .NET 版本控制有关的开发过程中会出现一个常见问题。  
  
 再次运行该进程时，更改不会生效。 这是由 .NET 程序集加载到内存中的方式造成的。 因为主机已经具有该程序集的内存中副本，所以在将新的副本放入全局程序集缓存中时，不会重新加载该程序集。 例如，部署并运行带有业务流程的版本 1.0.0.0 的程序集，如果对业务流程进行了更改而未更改版本号，则这些更改不会生效。 停止主机实例后将释放该程序集的内存中副本，重新启动该主机实例时，将重新加载该程序集的新副本并获取更改。 如果部署并加载了新的版本（例如版本 2.0.0.0），则更改生效。  
  
 将程序集部署到 BizTalk Server 的过程分两个部分。 第一部分是传统的 .NET 程序集部署，即在每个将使用强名称程序集的服务器上将该程序集部署到全局程序集缓存 (GAC)。 第二步是将有关这些程序集及其类型的元数据部署到 BizTalk Server 管理数据库。 BizTalk Server 加载 BizTalk Server 程序集时，通常使用这些程序集的强名称（可在管理数据库中找到）进行加载。  
  
## <a name="deploying-biztalk-server-assemblies-to-the-gac"></a>将 BizTalk Server 程序集部署到 GAC  
 开发人员创建的 BizTalk Server 项目将编译为从内置 BizTalk Server 类型派生的类。 例如，业务流程编译为从 Microsoft.BizTalkXLANGs.BTXEngine.BTXService 类派生的类。 由于这些基类部署到全局程序集缓存的程序集中，并且这些程序集对 GAC 中的其他程序集具有依存关系，因此还必须将开发人员的程序集部署到 GAC。  
  
 要部署到全局程序集缓存并因此要具有强名称的 BizTalk Server 项目的另一个重要含义是：强名称程序集不能调用还未具有强名称的程序集。 这意味着开发人员创建且由这些 BizTalk Server 程序集使用的任何程序集也必须具有强名称。 同样，如果部署到 GAC 的程序集不使用特定路径加载其他程序集，则必须从 GAC 加载这些程序集。  
  
 管道组件将被添加到开发人员的工具箱中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]以使它们可用拖动到管道设计器上。 将 BizTalk Server 管道编译为 .NET 程序集时，有关该管道各个阶段中的所有组件的信息将被编译到该程序集中。 此管道部署到 BizTalk Server，组件，包括各自的文件名称，有关的信息插入到 BizTalk 管理数据库和管道程序集部署到 GAC。 取决于 BizTalk 管道组件的任何其他程序集必须还将部署到 GAC 以便在运行时找到。 通过在运行时的 BizTalk 管道之前，还必须将管道组件程序集复制到 BizTalk Server\Pipeline 组件目录才能访问。 执行该管道时，将加载这些组件，并根据需要调用它们实现的接口。  
  
## <a name="see-also"></a>另请参阅  
 [运行时体系结构](../core/runtime-architecture.md)