---
title: "解决方案生成配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Configuration Manager
- building, solutions
- building, Configuration Manager
- solutions, deploying
- deploying, building
- solutions, developing
- solutions, build configuration
ms.assetid: 6f2cce47-388d-4c93-9146-768f53b8207e
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e537ca4bc2dd85722ddf3afd4eaba443aab7a25b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="solution-build-configurations"></a>解决方案生成配置
就像在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中生成的其他项目一样，您可以使用配置管理器来指定解决方案生成配置。 解决方案生成配置使你可以确定要在中包含的项目版本解决方案，并且如果将部署它们。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]同时支持**调试**和**版本**生成配置。  
  
 解决方案生成配置中的复选标记**生成**列使您能够构建一个解决方案，并在完成时生成的程序集。 如果还中存在一个复选标记，则**部署**列，然后再应用程序将部署基于项目设计器中的部署设置。  
  
 Configuration Manager 和配置的完整参考选项提供通过对话框框中，请参阅以下参考链接： [http://go.microsoft.com/fwlink/?LinkId=125365](http://go.microsoft.com/fwlink/?LinkId=125365)。  
  
### <a name="to-configure-build-properties-in-configuration-manager"></a>在配置管理器中配置生成属性  
  
1.  在“生成”  菜单上，单击“配置管理器” 。  
  
2.  在**Configuration Manager**对话框中，选择下列内容来配置生成属性之一。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**Configuration**|选择从**版本**或**调试**项目的配置。 另外，创建新配置或编辑现有配置。|  
    |**平台**|为项目选择一个表示已编译程序集 CPU 体系结构的平台。 另外，创建新平台或编辑现有平台。|  
    |**生成**|为了响应解决方案的构建命令，请为某个项目选中此列中的框，以构建或重新构建项目。|  
    |**部署**|选中此列中的框，以在针对解决方案或项目发出生成命令时，根据部署设置部署项目。|  
  
## <a name="see-also"></a>另请参阅  
 [如何部署 BizTalk 程序集，从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)   
 [如何创建 BizTalk 项目](../core/how-to-create-biztalk-projects.md)