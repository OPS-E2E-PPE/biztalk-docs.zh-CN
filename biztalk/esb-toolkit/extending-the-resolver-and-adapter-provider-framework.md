---
title: 扩展的解析程序和适配器提供程序框架 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4d5e6f2-b3bc-46e2-b8f7-d7e271d4a8c0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6ab5caf03d113e313e00a74c11641058e86b886
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294077"
---
# <a name="extending-the-resolver-and-adapter-provider-framework"></a><span data-ttu-id="ed1a3-102">扩展的解析程序和适配器提供程序框架</span><span class="sxs-lookup"><span data-stu-id="ed1a3-102">Extending the Resolver and Adapter Provider Framework</span></span>
<span data-ttu-id="ed1a3-103">它还可为服务提供自定义元数据和冲突解决程序和适配器提供程序框架的终结点和转换解析和路由、 提供支持。</span><span class="sxs-lookup"><span data-stu-id="ed1a3-103">The Resolver and Adapter Provider Framework provides support for endpoint and transformation resolution and routing, and it can also provide custom metadata for services.</span></span> <span data-ttu-id="ed1a3-104">框架可以动态解析终结点，并设置出站适配器属性。</span><span class="sxs-lookup"><span data-stu-id="ed1a3-104">The framework can dynamically resolve endpoints and set outbound adapter properties.</span></span> <span data-ttu-id="ed1a3-105">后一个冲突解决程序组件解析终结点 （例如，使用通用、 描述、 发现和集成 [UDDI] 若要查找的出站 URL），适配器提供程序组件设置的已注册 Microsoft BizTalk Server 适配器的特定属性。</span><span class="sxs-lookup"><span data-stu-id="ed1a3-105">After a resolver component resolves an endpoint (for example, using Universal Description, Discovery, and Integration [UDDI] to look up an outbound URL), an adapter provider component sets specific properties of registered Microsoft BizTalk Server adapters.</span></span>  
  
 <span data-ttu-id="ed1a3-106">有三个您可以在其中扩展中的冲突解决程序和适配器提供程序框架的主要方面：</span><span class="sxs-lookup"><span data-stu-id="ed1a3-106">There are three main areas where you can extend the Resolver and Adapter Provider Framework:</span></span>  
  
-   [<span data-ttu-id="ed1a3-107">创建自定义冲突解决程序</span><span class="sxs-lookup"><span data-stu-id="ed1a3-107">Creating a Custom Resolver</span></span>](../esb-toolkit/creating-a-custom-resolver.md)  
  
-   [<span data-ttu-id="ed1a3-108">使用 Unity 容器中创建自定义冲突解决程序</span><span class="sxs-lookup"><span data-stu-id="ed1a3-108">Creating a Custom Resolver with a Unity Container</span></span>](../esb-toolkit/creating-a-custom-resolver-with-a-unity-container.md)  
  
-   [<span data-ttu-id="ed1a3-109">创建自定义适配器提供程序</span><span class="sxs-lookup"><span data-stu-id="ed1a3-109">Creating a Custom Adapter Provider</span></span>](../esb-toolkit/creating-a-custom-adapter-provider.md)