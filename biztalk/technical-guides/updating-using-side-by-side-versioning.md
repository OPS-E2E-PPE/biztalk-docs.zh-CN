---
title: 更新使用的并行版本控制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9721a091-98ec-4f0b-ad1f-6ca184956e7c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6a247cebd665a5dc28f5b487d50b3432f7ff398
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261399"
---
# <a name="updating-using-side-by-side-versioning"></a>更新使用的并行版本控制
如果您不能计划停机时间，或者具有不能终止的长时间运行的业务流程实例，可能需要的并行版本控制。 在此类型的升级，两个版本的同一应用程序或应用程序项目运行的并行。 .NET 运行时本质上是允许的名称相同的但以不同的方式已进行版本管理程序集部署并运行，并且 BizTalk Server 还允许它。  
  
 通过并行版本控制的应用程序时，要推出升级主要应用程序以增量方式，例如使其可供业务合作伙伴的子集最初，而不是所有合作伙伴在一次。 使用此方法使您可以继续运行现有应用程序服务尚未使用新版本直到您就可以完全转换到新版本的用户。  
  
 不与通过递增版本号创建程序集版本相同的方式来创建应用程序版本。 相反，您创建新的应用程序具有与原始应用程序，不同的名称，并填充的新版本的应用程序项目。  
  
 因为许多类型的项目，如程序集，可以存在于 BizTalk 组中只有一个应用程序，则必须增加之前可以将它们部署到新的应用程序组中已存在的任何程序集的版本号。  
  
 分步更新的应用程序或业务流程使用的并行版本控制所需的任务的列表，请参阅[核对清单：更新应用程序使用的并行版本控制](../technical-guides/checklist-updating-an-application-using-side-by-side-versioning.md)和[核对清单：正在更新业务流程使用的并行版本控制](../technical-guides/checklist-updating-an-orchestration-using-side-by-side-versioning.md)。 有关如何通过并行部署的应用程序的详细说明，请参阅"[如何部署到运行并行应用程序与现有版本的新版本](http://go.microsoft.com/fwlink/?LinkId=155143)(<http://go.microsoft.com/fwlink/?LinkId=155143>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何使用并排版本控制更新映射](../technical-guides/how-to-update-a-map-using-side-by-side-versioning.md)  
  
-   [如何使用并排版本控制更新管道](../technical-guides/how-to-update-a-pipeline-using-side-by-side-versioning.md)  
  
-   [使用并排版本控制更新架构](../technical-guides/updating-a-schema-using-side-by-side-versioning.md)