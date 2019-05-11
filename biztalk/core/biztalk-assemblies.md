---
title: BizTalk Server 中的程序集的部署方式 |Microsoft Docs
description: 将程序集部署到 GAC 中，并在 BizTalk Server 中的程序集启用版本控制
ms.custom: ''
ms.date: 01/21/2016
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7f99ed5-b64a-4a38-99d7-83070fb69030
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b875a1fd724e9807362b23a5fa884cec3077f53d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358125"
---
# <a name="biztalk-assemblies"></a>BizTalk 程序集
Microsoft BizTalk Server 和.NET Framework 的最重要方面是，所有 BizTalk Server 项目;映射、 架构、 业务流程和管道，获取编译到.NET 程序集。 这种设计的两个最重要的意义是，这些程序集必须具有强名称，并且正因为如此，它们还需遵守.NET 版本控制规则。 其主要含义是，一次生成的其他.NET 项目或程序集 （包括 BizTalk 项目） 的特定版本的 BizTalk 项目，将继续使用该版本，直到它已针对较新版本重新生成。  
  
## <a name="net-versioning-and-assemblies"></a>.NET 版本控制和程序集  
 在 BizTalk 项目上的版本号不会更改，而不必停止和启动加载类型的 BizTalk 主机实例重新部署程序集时，与.NET 版本控制相关的开发过程中会出现一个常见问题。  
  
 再次运行该过程时，更改不会生效。 这是因为.NET 程序集加载到内存的方式。 因为主机已经具有该程序集的内存中副本，它不会重新加载该程序集时的新副本将放入全局程序集缓存。 例如，如果在部署与业务流程的程序集的版本 1.0.0.0 和对业务流程进行运行，并更改，但不是更改版本号，所做的更改不执行操作才会生效。 停止主机实例后，发布的程序集的内存中副本，该主机实例启动时再次它重新加载该程序集的新副本并获取所做的更改。 如果部署新版本，例如版本 2.0.0.0，并加载，则所做的更改生效。  
  
 将程序集部署到 BizTalk Server 是一个两部分过程。 第一部分是传统的.NET 程序集部署具有强名称程序集在其中部署到全局程序集缓存 (GAC) 中将使用该程序集的每个服务器上。 第二步是将有关程序集及其类型的元数据部署到 BizTalk Server 管理数据库。 时由 BizTalk Server 加载 BizTalk Server 程序集，它们通常将加载使用其强名称，在管理数据库中找到。  
  
## <a name="deploying-biztalk-server-assemblies-to-the-gac"></a>将 BizTalk Server 程序集部署到 GAC  
 开发人员创建的 BizTalk Server 项目将编译为从内置 BizTalk Server 类型中派生的类。 例如，业务流程将成为从 Microsoft.BizTalkXLANGs.BTXEngine.BTXService 类派生的类。 这是因为这些基类部署在程序集到全局程序集缓存，并且这些程序集位于 GAC 中的其他程序集具有依赖项也必须获取开发人员的程序集部署到 GAC。  
  
 另一个重要含义的 BizTalk Server 项目部署到全局程序集缓存，因此要具有强的名称，强名称程序集不能调用其他不还具有强名称的程序集。 这意味着任何开发人员创建的程序集，由这些 BizTalk Server 程序集也必须进行强名称。 同样，部署到 GAC，而无需使用特定路径加载其他程序集的程序集必须从 GAC 加载这些程序集。  
  
 向开发人员的工具箱中添加了管道组件[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，使它们可拖放到管道设计器。 BizTalk Server 管道编译为.NET 程序集，在各个阶段中管道的所有组件的相关信息获取编译成程序集。 此管道部署到 BizTalk Server，组件，包括其文件名称，有关的信息插入到 BizTalk 管理数据库和管道程序集部署到 GAC。 BizTalk 管道组件所依赖的任何其他程序集还必须部署到 GAC 这样才能在运行时找到。 通过 BizTalk 管道在运行时之前，还必须将管道组件程序集复制到 BizTalk Server\Pipeline 组件目录可以访问。 执行管道时，将加载这些组件，并根据需要调用它们实现的接口。  
  
## <a name="see-also"></a>请参阅  
 [运行时体系结构](../core/runtime-architecture.md)