---
title: 自定义绑定文件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, binding files
- binding files
- binding files, about binding files
- binding files, customizing
ms.assetid: 4714e6c2-4912-43aa-ba5a-0be06916a30a
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1534be96255084b963ed3883a1370af00f73b605
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238365"
---
# <a name="customizing-binding-files"></a><span data-ttu-id="66e8e-102">自定义绑定文件</span><span class="sxs-lookup"><span data-stu-id="66e8e-102">Customizing Binding Files</span></span>
<span data-ttu-id="66e8e-103">绑定文件是 XML 文件，用于描述 BizTalk 管理数据库中的项目以及这些项目之间的关系。</span><span class="sxs-lookup"><span data-stu-id="66e8e-103">Binding files are XML files that describe artifacts in a BizTalk Management database and the relationship between these artifacts.</span></span> <span data-ttu-id="66e8e-104">绑定文件可用于将配置信息从一个 BizTalk 配置数据库中导出，再将这些信息导入其他 BizTalk 配置数据库。</span><span class="sxs-lookup"><span data-stu-id="66e8e-104">Binding files are useful for exporting configuration information from one BizTalk configuration database and importing this information into another BizTalk configuration database.</span></span> <span data-ttu-id="66e8e-105">例如，开发人员可以在开发环境中设计一个 BizTalk 解决方案及其相关项目，然后将这些项目导出到某一绑定文件中，并最终将这些项目导入到某一生产环境。</span><span class="sxs-lookup"><span data-stu-id="66e8e-105">For example, a developer may design a BizTalk solution and its related artifacts in a development environment, then export these artifacts to a binding file and finally, import these artifacts into a production environment.</span></span> <span data-ttu-id="66e8e-106">您还可以使用绑定文件更新现有配置。</span><span class="sxs-lookup"><span data-stu-id="66e8e-106">You can also use a binding file to update an existing configuration.</span></span> <span data-ttu-id="66e8e-107">例如，您可以使用绑定文件将在开发环境中进行的配置更改应用于生产环境中。</span><span class="sxs-lookup"><span data-stu-id="66e8e-107">For example you can apply configuration changes made in a development environment to your production environment with a binding file.</span></span> <span data-ttu-id="66e8e-108">本主题介绍在使用绑定文件更新现有配置时需要注意的事项、绑定文件的结构以及可在绑定文件中设置的特定于适配器的配置属性。</span><span class="sxs-lookup"><span data-stu-id="66e8e-108">This topic discusses considerations when updating an existing configuration with a binding file, the structure of a binding file, and adapter specific configuration properties that can be set in a binding file.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="66e8e-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="66e8e-109">In This Section</span></span>  
  
-   [<span data-ttu-id="66e8e-110">与绑定文件更新现有配置</span><span class="sxs-lookup"><span data-stu-id="66e8e-110">Updating an Existing Configuration with a Binding File</span></span>](../core/updating-an-existing-configuration-with-a-binding-file.md)  
  
-   [<span data-ttu-id="66e8e-111">绑定文件的结构</span><span class="sxs-lookup"><span data-stu-id="66e8e-111">Structure of a Binding File</span></span>](../core/structure-of-a-binding-file.md)  
  
-   [<span data-ttu-id="66e8e-112">集成的 BizTalk 适配器的配置属性</span><span class="sxs-lookup"><span data-stu-id="66e8e-112">Configuration Properties for Integrated BizTalk Adapters</span></span>](../core/configuration-properties-for-integrated-biztalk-adapters.md)