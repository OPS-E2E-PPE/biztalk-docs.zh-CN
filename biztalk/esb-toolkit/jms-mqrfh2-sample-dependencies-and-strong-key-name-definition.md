---
title: JMS MQRFH2 示例依赖关系和强密钥名称定义 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3a5cdce-dcdf-48df-91a5-8cf2afce9255
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7079bc7475fa8310d64ff6925dd89e348afc195
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261538"
---
# <a name="jms-mqrfh2-sample-dependencies-and-strong-key-name-definition"></a><span data-ttu-id="a4e96-102">JMS MQRFH2 示例依赖关系和强密钥名称定义</span><span class="sxs-lookup"><span data-stu-id="a4e96-102">JMS MQRFH2 Sample Dependencies and Strong Key Name Definition</span></span>
<span data-ttu-id="a4e96-103">Visual Studio 项目 ESB。JMS。PipelineComponents 取决于以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="a4e96-103">The Visual Studio project ESB.JMS.PipelineComponents depends on the following folder:</span></span>  
  
-   <span data-ttu-id="a4e96-104">\<BizTalk Server 安装目录\>。</span><span class="sxs-lookup"><span data-stu-id="a4e96-104">\<BizTalk Server Installation Directory\>.</span></span> <span data-ttu-id="a4e96-105">此文件夹提供了对以下命名空间的访问：</span><span class="sxs-lookup"><span data-stu-id="a4e96-105">This folder provides access to the following namespaces:</span></span>  
  
    -   <span data-ttu-id="a4e96-106">**Microsoft::BizTalk::Message::Interop**</span><span class="sxs-lookup"><span data-stu-id="a4e96-106">**Microsoft::BizTalk::Message::Interop**</span></span>  
  
    -   <span data-ttu-id="a4e96-107">**Microsoft::BizTalk::Component::Interop**</span><span class="sxs-lookup"><span data-stu-id="a4e96-107">**Microsoft::BizTalk::Component::Interop**</span></span>  
  
## <a name="the-strong-name-key-definition"></a><span data-ttu-id="a4e96-108">强名称密钥定义</span><span class="sxs-lookup"><span data-stu-id="a4e96-108">The Strong Name Key Definition</span></span>  
 <span data-ttu-id="a4e96-109">通常情况下，强名称密钥定义驻留在的 AssemblyInfo.cpp 文件中。</span><span class="sxs-lookup"><span data-stu-id="a4e96-109">Usually, the strong-name key definition resides in the AssemblyInfo.cpp file.</span></span> <span data-ttu-id="a4e96-110">但是，这将与冲突C++读取的 AssemblyInfo.cpp 文件后，编译器将添加到该程序集的清单文件。</span><span class="sxs-lookup"><span data-stu-id="a4e96-110">However, this would conflict with the C++ manifest file that the compiler adds to the assembly after it reads the AssemblyInfo.cpp file.</span></span> <span data-ttu-id="a4e96-111">此冲突会阻止任何尝试将该文件放在全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="a4e96-111">This conflict would prevent any attempt to place the file in the global assembly cache.</span></span> <span data-ttu-id="a4e96-112">相反，链接器控件的强名称密钥文件通过指定密钥文件位于.../../../../../../ Keys/Microsoft.Practices.ESB.snk。</span><span class="sxs-lookup"><span data-stu-id="a4e96-112">Instead, the linker controls the strong name key file by specifying the key file located at ../../../../../../Keys/Microsoft.Practices.ESB.snk.</span></span> <span data-ttu-id="a4e96-113">若要编辑此值，导航到以下选项设置：</span><span class="sxs-lookup"><span data-stu-id="a4e96-113">To edit this value, navigate to the following option setting:</span></span>  
  
 <span data-ttu-id="a4e96-114">ESB。JMS。架构</span><span class="sxs-lookup"><span data-stu-id="a4e96-114">ESB.JMS.Schemas</span></span>  
  
 <span data-ttu-id="a4e96-115">\- 项目</span><span class="sxs-lookup"><span data-stu-id="a4e96-115">\- Project</span></span>  
  
 <span data-ttu-id="a4e96-116">\- -属性</span><span class="sxs-lookup"><span data-stu-id="a4e96-116">\- - Properties</span></span>  
  
 <span data-ttu-id="a4e96-117">\- --配置属性</span><span class="sxs-lookup"><span data-stu-id="a4e96-117">\- - - Configuration Properties</span></span>  
  
 <span data-ttu-id="a4e96-118">\- ---链接器</span><span class="sxs-lookup"><span data-stu-id="a4e96-118">\- - - - Linker</span></span>  
  
 <span data-ttu-id="a4e96-119">\- ----高级</span><span class="sxs-lookup"><span data-stu-id="a4e96-119">\- - - - - Advanced</span></span>  
  
 <span data-ttu-id="a4e96-120">\- -密钥文件</span><span class="sxs-lookup"><span data-stu-id="a4e96-120">\- - - - - - Key File</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4e96-121">如果构造 JMS 管道组件，则必须编辑 AssemblyInfo.cpp 文件以删除对强名称密钥文件，任何引用，如前面所述。</span><span class="sxs-lookup"><span data-stu-id="a4e96-121">If you construct a JMS Pipeline Component, you must edit the AssemblyInfo.cpp file to remove any references to the strong-name key file, as described earlier.</span></span> <span data-ttu-id="a4e96-122">完成该操作后，编辑**密钥文件**选项链接器的高级属性中指定的路径和强名称密钥文件的名称。</span><span class="sxs-lookup"><span data-stu-id="a4e96-122">After you do that, edit the **Key File** option in the advanced properties of the Linker to specify the path and name of the strong-name key file.</span></span>