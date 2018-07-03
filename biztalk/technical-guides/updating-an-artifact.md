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
ms.openlocfilehash: f32efa6195013d77ee368c0678a9ca67afb4e6e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980038"
---
# <a name="updating-an-artifact"></a>更新某一项目
在两个或多个 BizTalk 应用程序中的项目之间的依赖项可以具有显著影响应用程序部署和维护。 项目依赖于另一个需要使用该项目才能正常工作时，例如业务流程，需要使用特定管道以便正确传输消息。  
  
 若要更新的应用程序中的项目，您必须先取消部署它，以及依赖于它的所有项目。 在具有依存关系的多个项目存在于同一应用程序中时，BizTalk Server 自动处理更新的和依赖的项目的取消部署和重新部署任务。 但在具有依存关系的项目存在于不同应用程序时，就无法自动完成上述任务了。 如果你想要更新一个应用程序中的项目和其他应用程序中的项目有依赖关系，必须取消部署并按如下所示手动重新部署依赖的程序集：  
  
1. 停止、取消登记和取消绑定依赖的程序集。  
  
2. 更新它依赖的程序集。  
  
3. 绑定、登记和启动依赖的程序集。  
  
   若要无需执行手动步骤来更新某个项目上的其他项目所依赖，可以尝试使依赖项的所有项目保持在同一应用程序。 这并不总是有可能，但是，因为大多数类型的项目必须是 BizTalk 组中唯一。 您不能在同一组的两个不同应用程序中具有相同的项目，即使这两个应用程序都包含依赖于相同项目的项目。 有关该问题的唯一项目的详细信息，请参阅[项目，必须是唯一的应用程序或组](http://go.microsoft.com/fwlink/?LinkId=155141)(<http://go.microsoft.com/fwlink/?LinkId=155141>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
   您可以将所需的项目添加到一个应用程序，然后添加对该应用程序中包含的项目的依赖于它的任何其他应用程序的引用。 在您添加对某一应用程序的引用时，该应用程序中的项目可以使用它引用的应用程序中的任何项目。 有关添加引用的说明，请参阅[如何添加对另一个应用程序的引用](http://go.microsoft.com/fwlink/?LinkID=155011)(<http://go.microsoft.com/fwlink/?LinkID=155011>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
   用于更新 BizTalk 应用程序中的项目的任务的清单，请参阅[清单： 更新 BizTalk 应用程序中的项目](http://go.microsoft.com/fwlink/?LinkId=155647)(<http://go.microsoft.com/fwlink/?LinkId=155647>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
## <a name="see-also"></a>请参阅  
 [更新应用程序和项目](../technical-guides/updating-applications-and-artifacts.md)