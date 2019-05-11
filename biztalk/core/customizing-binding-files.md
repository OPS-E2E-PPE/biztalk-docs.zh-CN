---
title: 自定义绑定文件 |Microsoft Docs
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
ms.openlocfilehash: 74322134891c7f52f9892d4c658d897fb95f9305
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390012"
---
# <a name="customizing-binding-files"></a>自定义绑定文件
绑定文件是描述 BizTalk 管理数据库和这些项目之间的关系中的项目的 XML 文件。 绑定文件可用于从一个 BizTalk 配置数据库中导出配置信息并导入另一个 BizTalk 配置数据库的此信息。 例如，开发人员可能设计一个 BizTalk 解决方案，并在开发环境中，及其相关的项目，然后将这些项目导出到绑定文件和最后，这些项目导入到生产环境。 绑定文件还可用于更新现有配置。 例如可以应用与绑定文件一起在开发环境与生产环境中进行的配置更改。 更新现有配置与绑定文件中，绑定文件，并可以在绑定文件中设置的适配器特定的配置属性的结构时，本主题讨论的注意事项。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用绑定文件更新现有配置](../core/updating-an-existing-configuration-with-a-binding-file.md)  
  
-   [绑定文件的结构](../core/structure-of-a-binding-file.md)  
  
-   [配置集成的 BizTalk 适配器的属性](../core/configuration-properties-for-integrated-biztalk-adapters.md)