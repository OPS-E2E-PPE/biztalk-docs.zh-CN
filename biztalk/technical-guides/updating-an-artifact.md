---
title: "更新某个项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40feab57-4286-4bdf-8f52-25d02b3fa60c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17d5f2ad910c59ded9c2499c929d73480fac7b51
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="updating-an-artifact"></a>更新某个项目
在两个或多个 BizTalk 应用程序中的项目之间的依赖关系可以显著影响应用程序部署和维护。 它需要使用该项目才能正常运行时依赖于另一个项目，例如业务流程，需要使用特定的管道，以正确传输消息。  
  
 若要更新应用程序中的项目，必须首先取消它，部署以及任何依赖于它的项目中。 在具有依存关系的多个项目存在于同一应用程序中时，BizTalk Server 自动处理更新的和依赖的项目的取消部署和重新部署任务。 但在具有依存关系的项目存在于不同应用程序时，就无法自动完成上述任务了。 如果你想要更新的应用程序中，项目和其他应用程序中的项目具有的依赖关系，你必须取消部署并，如下所示手动重新部署依赖项目：  
  
1.  停止、取消登记和取消绑定依赖的程序集。  
  
2.  更新它依赖的程序集。  
  
3.  绑定、登记和启动依赖的程序集。  
  
 若要避免需要执行手动步骤来更新上的项目的其他项目依赖，你可以尝试将具有依赖项的所有项目都放在同一个应用程序。 这并不总是有可能，但是，由于大多数类型的项目必须是唯一 BizTalk 组中。 您不能在同一组的两个不同应用程序中具有相同的项目，即使这两个应用程序都包含依赖于相同项目的项目。 有关问题的唯一项目的详细信息，请参阅[项目，必须是唯一的应用程序或组](http://go.microsoft.com/fwlink/?LinkId=155141)(http://go.microsoft.com/fwlink/?LinkId=155141) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
 你可以将所需的项目添加到一个应用程序，然后添加对该应用程序中包含依赖于它的项目的任何其他应用程序的引用。 在您添加对某一应用程序的引用时，该应用程序中的项目可以使用它引用的应用程序中的任何项目。 有关添加引用的说明，请参阅[如何添加对另一个应用程序的引用](http://go.microsoft.com/fwlink/?LinkID=155011)(http://go.microsoft.com/fwlink/?LinkID=155011) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
 用于更新 BizTalk 应用程序中的项目的任务的清单，请参阅[清单： 更新 BizTalk 应用程序中的项目](http://go.microsoft.com/fwlink/?LinkId=155647)(http://go.microsoft.com/fwlink/?LinkId=155647) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
## <a name="see-also"></a>另请参阅  
 [更新应用程序和项目](../technical-guides/updating-applications-and-artifacts.md)