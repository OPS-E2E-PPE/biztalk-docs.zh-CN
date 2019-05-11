---
title: 将项目添加到应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a9b5e92e-2e55-41d7-9959-f62753bbeb04
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ac647201a834d90d745564076b040954c1c3667
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401411"
---
# <a name="adding-artifacts-to-an-application"></a>将项目添加到应用程序
可以添加和配置项目，例如发送和接收端口、 接收位置和业务流程，使用管理控制台。 您还可以生成绑定文件并将其添加到应用程序中，如果你想要应用于不同的环境，您将导入到应用程序的不同绑定。  
  
 您可以添加其他 (通常非 BizTalk Server) 项目，如脚本、 证书和自述文件、 到资源节点下的应用程序。 若要执行此操作，使用管理控制台或 BTSTask。  
  
 有关项目的详细信息，请参阅[如何创建或添加项目](http://go.microsoft.com/fwlink/?LinkID=154724)(http://go.microsoft.com/fwlink/?LinkID=154724)，[管理项目](http://go.microsoft.com/fwlink/?LinkID=154725)(http://go.microsoft.com/fwlink/?LinkID=154725)和[绑定文件和应用程序部署](http://go.microsoft.com/fwlink/?LinkID=154726) (http://go.microsoft.com/fwlink/?LinkID=154726).  
  
## <a name="factoring-artifacts-into-multiple-biztalk-applications"></a>分解为多个 BizTalk 应用程序的项目  
 在开发过程中，你可能已部署您的程序集到单一应用程序中为方便起见。 由于各种原因，你可能想要部署到生产环境之前，将项目分解到多个应用程序。  
  
 在部署之前，应执行程序集的分解情况的深入的分析。 确定是否应执行任何分解、 完整分解或者最佳分解。  
  
 **没有分解**  
  
 所有 BizTalk 项目都是在一个程序集中。 这是最容易了解和部署，但可以最大的灵活性。  
  
 **完整分解**  
  
 每个 BizTalk 项目是在自己的程序集。 这提供了最大的灵活性，但最复杂部署和了解。  
  
 **最佳分解**  
  
 最佳分解介于之间无分解和完整分解基于 BizTalk 应用程序的深入分析。 除了版本控制，这样，您可以更轻松地实现您的 BizTalk 主机设计。 这被通过查找 BizTalk 项目之间的关系。 如果可能，将始终在同一程序集版本控制的项目。 如果需要独立的版本控制的项目，然后它们必须放入不同的程序集。 这是你想要实现的分解级别。