---
title: "自定义绑定文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, binding files
- binding files
- binding files, about binding files
- binding files, customizing
ms.assetid: 4714e6c2-4912-43aa-ba5a-0be06916a30a
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1534be96255084b963ed3883a1370af00f73b605
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="customizing-binding-files"></a>自定义绑定文件
绑定文件是 XML 文件，用于描述 BizTalk 管理数据库中的项目以及这些项目之间的关系。 绑定文件可用于将配置信息从一个 BizTalk 配置数据库中导出，再将这些信息导入其他 BizTalk 配置数据库。 例如，开发人员可以在开发环境中设计一个 BizTalk 解决方案及其相关项目，然后将这些项目导出到某一绑定文件中，并最终将这些项目导入到某一生产环境。 您还可以使用绑定文件更新现有配置。 例如，您可以使用绑定文件将在开发环境中进行的配置更改应用于生产环境中。 本主题介绍在使用绑定文件更新现有配置时需要注意的事项、绑定文件的结构以及可在绑定文件中设置的特定于适配器的配置属性。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [与绑定文件更新现有配置](../core/updating-an-existing-configuration-with-a-binding-file.md)  
  
-   [绑定文件的结构](../core/structure-of-a-binding-file.md)  
  
-   [集成的 BizTalk 适配器的配置属性](../core/configuration-properties-for-integrated-biztalk-adapters.md)