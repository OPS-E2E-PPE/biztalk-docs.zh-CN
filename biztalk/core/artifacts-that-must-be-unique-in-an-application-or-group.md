---
title: 中的应用程序或组必须是唯一的项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, artifacts
- artifacts, requirements
- applications, artifacts
ms.assetid: a758cd74-a962-4e75-aea2-47752ab72a64
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dc28a438dff5e2fe21dc00d207da64fbdd2fc69
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359256"
---
# <a name="artifacts-that-must-be-unique-in-an-application-or-group"></a>中的应用程序或组必须是唯一的项目
某些类型的 BizTalk 组或应用程序中的项目必须唯一，按如下所示：  
  
- 在组中，BizTalk 程序集和非 BizTalk.NET 程序集必须具有唯一的全名。 全名包括文件名、 公钥标记、 区域性和版本。  
  
- 规则和策略必须具有唯一的名称和版本编号的组中。  
  
- 发送端口、 发送端口组、 接收端口和接收位置必须具有在组中唯一的名称。  
  
- 网站必须在组中具有唯一的虚拟目录名称。  
  
- 在组中，BAM 资源必须具有唯一的文件名。  
  
- 在组中，证书必须具有唯一的指纹。  
  
- COM 组件必须在组中具有唯一的文件名。  
  
- 在应用程序，但不是在组中，基于文件的项目，如脚本和其他平面文件，必须具有唯一的文件名称。  
  
  可以指定覆盖选项导入或将项目添加到应用程序，如果应用程序中已存在该项目并且它必须是唯一的应用程序中的类型。 如果项目已存在的组中，另一个应用程序中，并且它是类型必须是唯一的组中，您不能添加或导入它。  
  
  如果您需要使用一个应用程序中的项目，并且它已存在于组中的另一个应用程序，可以创建对包含该项目的应用程序的引用。 有关详细信息请参阅[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。  
  
> [!NOTE]
>  您可以查看大多数类型的项目的完整名称的应用程序中使用 BTSTask，ListApp 命令中所述[ListApp 命令](../core/listapp-command.md)。  
  
## <a name="see-also"></a>请参阅  
 [了解 BizTalk 应用程序的部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)