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
ms.openlocfilehash: fb81ffe1f97681f82ddc3d45b9d93ff34b5e172a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023259"
---
# <a name="artifacts-that-must-be-unique-in-an-application-or-group"></a>在应用程序或组中必须唯一的项目
BizTalk 组或 BizTalk 应用程序中某些项目类型必须是唯一的，如下所述。  
  
- BizTalk 程序集和非 BizTalk .NET 程序集必须具有在组中唯一的全名。 全名包括文件名、公钥标记、区域性和版本。  
  
- 规则和策略必须具有在组中唯一的名称和版本号。  
  
- 发送端、发送端口组、接收端口和接收位置必须具有在组中唯一的名称。  
  
- 网站必须具有在组中唯一的虚拟目录名称。  
  
- BAM 资源必须具有在组中唯一的文件名。  
  
- 证书必须具有在组中唯一的指纹。  
  
- COM 组件必须具有在组中唯一的文件名。  
  
- 基于文件的项目，如脚本和其他平面文件，必须具有在应用程序中而不是在组中唯一的文件名。  
  
  在向应用程序中导入或添加项目时，如果该项目在应用程序中已存在，并且其类型在应用程序中必须唯一，则可以指定覆盖选项。 如果该项目已存在于组中的另一个应用程序中，并且其类型在组中必须唯一，您既不能添加它，也不能导入它。  
  
  如果需要使用一个应用程序中的项目并且它已存在于组中的另一个应用程序中，您可以创建对包含该项目的应用程序的引用。 有关详细信息请参阅[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。  
  
> [!NOTE]
>  您可以查看大多数类型的项目的完整名称的应用程序中使用 BTSTask，ListApp 命令中所述[ListApp 命令](../core/listapp-command.md)。  
  
## <a name="see-also"></a>请参阅  
 [了解 BizTalk 应用程序的部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)