---
title: 更新某一项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40feab57-4286-4bdf-8f52-25d02b3fa60c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4744fa7181e1ee290357f0a694e326e2ac22e1f2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261410"
---
# <a name="updating-an-artifact"></a>更新某一项目
在两个或多个 BizTalk 应用程序中的项目之间的依赖项可以具有显著影响应用程序部署和维护。 项目依赖于另一个需要使用该项目才能正常工作时，例如业务流程，需要使用特定管道以便正确传输消息。  
  
 若要更新的应用程序中的项目，您必须先取消部署它，以及依赖于它的所有项目。 项目的依赖关系存在于同一应用程序中，BizTalk Server 将自动处理更新和依赖的项目取消部署和重新部署任务。 当项目的依赖关系存在于不同的应用程序中时，但是，这不是种。 如果你想要更新一个应用程序中的项目和其他应用程序中的项目有依赖关系，必须取消部署并按如下所示手动重新部署依赖的程序集：  
  
1. 停止、 取消登记和取消绑定依赖的程序集。  
  
2. 更新所依赖的项目。  
  
3. 将绑定、 登记并启动依赖的程序集。  
  
   若要无需执行手动步骤来更新某个项目上的其他项目所依赖，可以尝试使依赖项的所有项目保持在同一应用程序。 这并不总是有可能，但是，因为大多数类型的项目必须是 BizTalk 组中唯一。 不能在同一组中的两个不同应用程序中具有相同的项目，即使这两个应用程序包含依赖于相同的项目的项目。 有关该问题的唯一项目的详细信息，请参阅[项目，必须是唯一的应用程序或组](http://go.microsoft.com/fwlink/?LinkId=155141)(<http://go.microsoft.com/fwlink/?LinkId=155141>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
   您可以将所需的项目添加到一个应用程序，然后添加对该应用程序中包含的项目的依赖于它的任何其他应用程序的引用。 时添加到应用程序的引用，请在应用程序中的项目可以使用它所引用的应用程序中的所有项目。 有关添加引用的说明，请参阅[如何添加对另一个应用程序的引用](http://go.microsoft.com/fwlink/?LinkID=155011)(<http://go.microsoft.com/fwlink/?LinkID=155011>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
   用于更新 BizTalk 应用程序中的项目的任务的清单，请参阅[核对清单：更新 BizTalk 应用程序中的项目](http://go.microsoft.com/fwlink/?LinkId=155647)(<http://go.microsoft.com/fwlink/?LinkId=155647>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
## <a name="see-also"></a>请参阅  
 [更新应用程序和项目](../technical-guides/updating-applications-and-artifacts.md)