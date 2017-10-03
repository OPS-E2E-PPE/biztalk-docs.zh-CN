---
title: "部署管道组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, pipeline components [custom]
- pipeline components [custom], deploying
ms.assetid: 98b47fbf-62c0-4012-a406-58c4d56b305a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84ee3255c38e26c5f5d6d19797cba03ba549668b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-pipeline-components"></a><span data-ttu-id="29426-102">部署管道组件</span><span class="sxs-lookup"><span data-stu-id="29426-102">Deploying Pipeline Components</span></span>
<span data-ttu-id="29426-103">所有.NET 管道组件程序集 （本机和自定义） 必须都位于\<*安装目录*> 要由服务器执行的 \Pipeline 组件文件夹。</span><span class="sxs-lookup"><span data-stu-id="29426-103">All the .NET pipeline component assemblies (native and custom) must be located in the \<*installation directory*>\Pipeline Components folder to be executed by the server.</span></span> <span data-ttu-id="29426-104">如果将在多台服务器部署管道与自定义组件，组件的二进制文件必须存在的每个服务器上的指定文件夹中。</span><span class="sxs-lookup"><span data-stu-id="29426-104">If the pipeline with a custom component will be deployed across several servers, the component's binaries must be present in the specified folder on every server.</span></span>  
  
 <span data-ttu-id="29426-105">不需要添加要由 BizTalk 运行到全局程序集缓存 (GAC) 中使用的自定义管道组件。</span><span class="sxs-lookup"><span data-stu-id="29426-105">You do not need to add a custom pipeline component to be used by the BizTalk Runtime to the Global Assembly Cache (GAC).</span></span>  
  
 <span data-ttu-id="29426-106">在工具箱中，还将显示在管道中的自定义 COM 组件，提供注册 COM 组件的计算机上。</span><span class="sxs-lookup"><span data-stu-id="29426-106">Custom COM components in the pipeline will also appear in the Toolbox, provided they are registered on the computer as a COM component.</span></span> <span data-ttu-id="29426-107">自定义.NET 管道组件必须放入\<*安装目录*> \Pipeline 组件文件夹。</span><span class="sxs-lookup"><span data-stu-id="29426-107">Custom .NET pipeline components must be placed into the \<*installation directory*>\Pipeline Components folder.</span></span>  
  
 <span data-ttu-id="29426-108">二进制文件位于正确的位置后，你需要将该组件添加到工具箱。</span><span class="sxs-lookup"><span data-stu-id="29426-108">After the binary files are in the correct location, you need to add the component to the Toolbox.</span></span> <span data-ttu-id="29426-109">将管道组件添加到工具箱中的说明，请参阅[如何使用工具箱](../core/how-to-use-the-toolbox.md)。</span><span class="sxs-lookup"><span data-stu-id="29426-109">For instructions on adding the pipeline component to the Toolbox, see [How to Use the Toolbox](../core/how-to-use-the-toolbox.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29426-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29426-110">See Also</span></span>  
 [<span data-ttu-id="29426-111">开发自定义管道组件</span><span class="sxs-lookup"><span data-stu-id="29426-111">Developing Custom Pipeline Components</span></span>](../core/developing-custom-pipeline-components.md)