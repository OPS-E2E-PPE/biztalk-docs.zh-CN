---
title: 解决方案生成配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e67898e3e24b98f9efbe92494e0f7fbe28b2fba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244323"
---
# <a name="solution-build-configurations"></a>解决方案生成配置
与您在生成其他项目一样[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，可以使用配置管理器来指定解决方案生成配置。 解决方案生成配置，可以确定解决方案的生成中包含的项目中，如果将部署它们。 BizTalk Server 同时支持两者**调试**并**发行**生成配置。  
  
 一种解决方案生成配置中的复选标记**生成**列，您可以构建解决方案，并在完成时生成的程序集。 如果一个复选标记还处在**部署**列，然后再应用程序将部署根据项目设计器中的部署设置。  
  
 配置管理器和配置的完整参考资料选项提供由对话框框中，请参阅以下参考链接： [ http://go.microsoft.com/fwlink/?LinkId=125365 ](http://go.microsoft.com/fwlink/?LinkId=125365)。  
  
### <a name="to-configure-build-properties-in-configuration-manager"></a>若要配置 Configuration Manager 中的生成属性  
  
1.  在“生成”  菜单上，单击“配置管理器” 。  
  
2.  在中**Configuration Manager**对话框中，选择以下操作来配置生成属性之一。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**Configuration**|选择从**发行**或**调试**项目配置。 或者，创建新的配置或编辑现有。|  
    |**平台**|选择一个平台，用于表示已编译的程序集的 CPU 体系结构的项目。 或者，创建一个新的平台或编辑现有。|  
    |**生成**|检查项目的项目生成或重新生成解决方案的构建命令的响应中此列中的框。|  
    |**部署**|检查此列可以具有部署的项目中的框的解决方案或项目发出生成命令时根据部署设置。|  
  
## <a name="see-also"></a>请参阅  
 [如何部署 BizTalk 程序集从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)   
 [如何创建 BizTalk 项目](../core/how-to-create-biztalk-projects.md)