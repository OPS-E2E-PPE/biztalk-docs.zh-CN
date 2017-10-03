---
title: "JMS MQRFH2 示例依赖关系和强密钥名称定义 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3a5cdce-dcdf-48df-91a5-8cf2afce9255
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1933fb0b15d7b948229edf537ec4b0b80071014b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="jms-mqrfh2-sample-dependencies-and-strong-key-name-definition"></a><span data-ttu-id="6cc72-102">JMS MQRFH2 示例依赖关系和强密钥名称定义</span><span class="sxs-lookup"><span data-stu-id="6cc72-102">JMS MQRFH2 Sample Dependencies and Strong Key Name Definition</span></span>
<span data-ttu-id="6cc72-103">[!INCLUDE[vs2010](../includes/vs2010-md.md)]项目 ESB。JMS。PipelineComponents 取决于以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="6cc72-103">The [!INCLUDE[vs2010](../includes/vs2010-md.md)] project ESB.JMS.PipelineComponents depends on the following folder:</span></span>  
  
-   <span data-ttu-id="6cc72-104">\<BizTalk Server 安装目录 >。</span><span class="sxs-lookup"><span data-stu-id="6cc72-104">\<BizTalk Server Installation Directory>.</span></span> <span data-ttu-id="6cc72-105">此文件夹提供了对以下命名空间的访问：</span><span class="sxs-lookup"><span data-stu-id="6cc72-105">This folder provides access to the following namespaces:</span></span>  
  
    -   <span data-ttu-id="6cc72-106">**Microsoft::BizTalk::Message::Interop**</span><span class="sxs-lookup"><span data-stu-id="6cc72-106">**Microsoft::BizTalk::Message::Interop**</span></span>  
  
    -   <span data-ttu-id="6cc72-107">**Microsoft::BizTalk::Component::Interop**</span><span class="sxs-lookup"><span data-stu-id="6cc72-107">**Microsoft::BizTalk::Component::Interop**</span></span>  
  
## <a name="the-strong-name-key-definition"></a><span data-ttu-id="6cc72-108">强名称密钥定义</span><span class="sxs-lookup"><span data-stu-id="6cc72-108">The Strong Name Key Definition</span></span>  
 <span data-ttu-id="6cc72-109">通常情况下，强名称密钥定义驻留在的 AssemblyInfo.cpp 文件中。</span><span class="sxs-lookup"><span data-stu-id="6cc72-109">Usually, the strong-name key definition resides in the AssemblyInfo.cpp file.</span></span> <span data-ttu-id="6cc72-110">但是，这会与 c + + 清单文件，它读取的 AssemblyInfo.cpp 文件之后，编译器将添加到程序集冲突。</span><span class="sxs-lookup"><span data-stu-id="6cc72-110">However, this would conflict with the C++ manifest file that the compiler adds to the assembly after it reads the AssemblyInfo.cpp file.</span></span> <span data-ttu-id="6cc72-111">此冲突将阻止任何尝试将文件放在全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="6cc72-111">This conflict would prevent any attempt to place the file in the global assembly cache.</span></span> <span data-ttu-id="6cc72-112">相反，链接器将通过指定密钥文件位于控制强名称密钥文件.../../../../../../ Keys/Microsoft.Practices.ESB.snk。</span><span class="sxs-lookup"><span data-stu-id="6cc72-112">Instead, the linker controls the strong name key file by specifying the key file located at ../../../../../../Keys/Microsoft.Practices.ESB.snk.</span></span> <span data-ttu-id="6cc72-113">若要编辑此值，导航到以下选项设置：</span><span class="sxs-lookup"><span data-stu-id="6cc72-113">To edit this value, navigate to the following option setting:</span></span>  
  
 <span data-ttu-id="6cc72-114">ESB。JMS。架构</span><span class="sxs-lookup"><span data-stu-id="6cc72-114">ESB.JMS.Schemas</span></span>  
  
 <span data-ttu-id="6cc72-115">\- 项目</span><span class="sxs-lookup"><span data-stu-id="6cc72-115">\- Project</span></span>  
  
 <span data-ttu-id="6cc72-116">\--属性</span><span class="sxs-lookup"><span data-stu-id="6cc72-116">\- - Properties</span></span>  
  
 <span data-ttu-id="6cc72-117">\---配置属性</span><span class="sxs-lookup"><span data-stu-id="6cc72-117">\- - - Configuration Properties</span></span>  
  
 <span data-ttu-id="6cc72-118">\----链接器</span><span class="sxs-lookup"><span data-stu-id="6cc72-118">\- - - - Linker</span></span>  
  
 <span data-ttu-id="6cc72-119">\-----高级</span><span class="sxs-lookup"><span data-stu-id="6cc72-119">\- - - - - Advanced</span></span>  
  
 <span data-ttu-id="6cc72-120">\------密钥文件</span><span class="sxs-lookup"><span data-stu-id="6cc72-120">\- - - - - - Key File</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6cc72-121">如果你构造 JMS 管道组件，则必须编辑 AssemblyInfo.cpp 文件，以删除对的强名称密钥文件的任何引用，如前面所述。</span><span class="sxs-lookup"><span data-stu-id="6cc72-121">If you construct a JMS Pipeline Component, you must edit the AssemblyInfo.cpp file to remove any references to the strong-name key file, as described earlier.</span></span> <span data-ttu-id="6cc72-122">完成该操作后，编辑**密钥文件**链接器的高级属性中的选项以指定的路径和强名称密钥文件的名称。</span><span class="sxs-lookup"><span data-stu-id="6cc72-122">After you do that, edit the **Key File** option in the advanced properties of the Linker to specify the path and name of the strong-name key file.</span></span>