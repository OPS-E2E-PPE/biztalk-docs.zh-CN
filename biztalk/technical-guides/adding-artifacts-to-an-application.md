---
title: 将项目添加到应用程序 |Microsoft 文档
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
ms.openlocfilehash: 2c08fa95dddad06efb2c51d93df56b757ae4caca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295645"
---
# <a name="adding-artifacts-to-an-application"></a>将项目添加到应用程序
你可以添加和配置项目，比如发送和接收端口、 接收位置和业务流程，通过使用管理控制台。 你还可以生成绑定文件，并将其添加到应用程序中，如果你想要应用的不同环境中将导入到应用程序的不同绑定。  
  
 你可以添加其他 (通常非 BizTalk Server) 项目，比如脚本、 证书和自述文件，为资源节点下的应用程序。 为此，请使用管理控制台或 BTSTask。  
  
 有关项目的详细信息，请参阅[如何创建或添加项目](http://go.microsoft.com/fwlink/?LinkID=154724)(http://go.microsoft.com/fwlink/?LinkID = 154724)，[管理项目](http://go.microsoft.com/fwlink/?LinkID=154725)(http://go.microsoft.com/fwlink/?LinkID = 154725) 和[绑定文件和应用程序部署](http://go.microsoft.com/fwlink/?LinkID=154726)(http://go.microsoft.com/fwlink/?LinkID = 154726)。  
  
## <a name="factoring-artifacts-into-multiple-biztalk-applications"></a>将项目分解为多个 BizTalk 应用程序  
 在开发过程中，出于方便，您可能会将程序集部署到单个应用程序中。 由于许多原因，您可能要将项目分解到多个应用程序中，然后再将它们部署到生产中。  
  
 在部署之前，应执行的程序集分解的深入分析。 确定是否应执行任何将分解、 完整分解或者最佳将分解。  
  
 **没有将分解**  
  
 BizTalk 中的所有项目都都在一个程序集中。 这是最容易了解和部署，但可以最大的灵活性。  
  
 **完整将分解**  
  
 每个 BizTalk 项目位于其自己的程序集中。 这提供了最大的灵活性，但最复杂部署并了解。  
  
 **最佳将分解**  
  
 最佳将分解介于之间否将分解和完整分解基于 BizTalk 应用程序的深入分析。 除了版本控制，这允许你更轻松地实现您的 BizTalk 主机设计。 这被通过寻找 BizTalk 项目之间的关系。 如果可能，将始终是版本控制的同一程序集中在一起的项目。 如果需要的项目的独立版本控制，然后必须将它们置于不同的程序集中。 这是你想要实现分解的级别。