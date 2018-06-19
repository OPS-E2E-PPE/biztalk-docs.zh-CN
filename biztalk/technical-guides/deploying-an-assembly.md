---
title: 部署程序集 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65f8ee21-0e52-4a74-b114-864a3069659c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73112fd9efb536452b8641faa976f42bb892b67c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297861"
---
# <a name="deploying-an-assembly"></a>部署程序集
部署程序集生成程序集，并将其，以及业务流程、 管道、 架构和映射 （项目），它将包含的本地 BizTalk 管理数据库导入。 最初，这可在开发环境中。  
  
 部署还将与 BizTalk 应用程序已在 Visual Studio 中的项目属性中指定关联程序集。 在您部署某一解决方案后，可以从 BizTalk Server 管理控制台内或通过使用 BTSTask 命令行工具查看和管理已部署的程序集及其项目。 你可以管理这些项目可以单独或应用程序中已分组。  
  
## <a name="deploying-an-assembly"></a>部署程序集  
 通过以下方式，可以将程序集添加到应用程序：  
  
-   将程序集部署到从 Visual Studio 环境中的应用程序  
  
-   手动将 BizTalk Server 程序集添加到从 BizTalk Server 管理控制台中的应用程序  
  
-   通过从命令行的脚本将 BizTalk 程序集添加到应用程序  
  
-   将 BizTalk Server 程序集移从 BizTalk Server 管理控制台中其他应用程序  
  
 有关将程序集添加到应用程序的详细信息，请参阅[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](http://go.microsoft.com/fwlink/?LinkID=154719) (http://go.microsoft.com/fwlink/?LinkID=154719)。  
  
## <a name="redeploying-assemblies"></a>重新部署程序集  
 在过程中开发和调试你的 BizTalk 程序集，你可能需要将其重新部署多次。 BizTalk Server 提供简单的机制，用于重新部署。 如果要重新程序集部署而无需更改的版本号，你可以使用重新部署属性。 BizTalk Server 将自动执行的所有步骤后，重新部署你的程序集。  
  
 有关重新部署程序集的详细信息，请参阅[如何重新部署 BizTalk 程序集从 Visual Studio](http://go.microsoft.com/fwlink/?LinkID=154720) (http://go.microsoft.com/fwlink/?LinkID=154720)。  
  
### <a name="best-practices-for-redeploying-an-assembly"></a>重新部署程序集的最佳做法  
 **你必须在 gac 中安装新的程序集**  
  
-   当你重新部署程序集时，始终必须安装在全局程序集缓存 (GAC) 中的程序集的新版本。 重新部署程序集后可实现此目的。 有关详细信息，请参阅[如何将程序集安装在 GAC 中](http://go.microsoft.com/fwlink/?LinkID=154828)(http://go.microsoft.com/fwlink/?LinkID=154828)。  
  
 **你应始终重新部署解决方案级别时不存在依赖关系**  
  
-   如果解决方案中有多个程序集，并且解决方案中的一个或多个程序集对要重新部署的程序集具有依存关系，则应在解决方案级重新部署程序集。 这是因为 BizTalk Server 时重新部署项目级别的程序集，将停止，取消登记，解除绑定，并删除中的所有程序集依赖于此程序集或在此程序集所依赖的项。 BizTalk Server 不会执行额外的步骤来部署、绑定、登记以及启动这些项目。 但是，在重新部署整个解决方案时，BizTalk Server 将根据解决方案中所有项目的依存关系，自动执行所需步骤来取消部署和重新部署这些项目。  
  
 **你可能需要手动重新部署依赖程序集**  
  
-   BizTalk Server 始终取消部署依赖程序集时它取消部署程序集，但是在以下情况下，您必须采取附加步骤以部署，将绑定，并登记中每个依赖程序集后重新部署在其上的程序集的项目依赖程序集：  
  
     在项目级重新部署了某个程序集，同一解决方案中的另一个程序集依赖于此程序集。  
  
     在解决方案级重新部署了某个程序集，但依存程序集存在于其他解决方案中。  
  
 **必须重启主机实例**  
  
-   在不更改程序集版本号的情况下重新部署包含业务流程的程序集时，BizTalk 管理数据库中的现有程序集将被覆盖。 不过，在更改生效之前，必须重新启动该业务流程绑定到的主机的所有主机实例。 你可以指定在重新部署程序集时自动重新启动本地计算机上的所有主机实例。  
  
     在不更改程序集版本号的情况下重新部署包含业务流程的程序集时，BizTalk 管理数据库中的现有程序集将被覆盖。 不过，在更改生效之前，必须重新启动该业务流程绑定到的主机的所有主机实例。 你可以指定在重新部署程序集时自动重新启动本地计算机上的所有主机实例。 有关部署属性的详细信息，请参阅[如何在 Visual Studio 中设置部署属性](http://go.microsoft.com/fwlink/?LinkID=154718)(http://go.microsoft.com/fwlink/?LinkID=154718)。  
  
     你可以手动停止和启动每个主机实例。 有关停止和启动主机实例的详细信息，请参阅[如何停止主机实例](http://go.microsoft.com/fwlink/?LinkID=154829)(http://go.microsoft.com/fwlink/?LinkID = 154829) 和[如何启动的主机实例](http://go.microsoft.com/fwlink/?LinkID=154830)(http://go.microsoft.com/fwlink/?LinkID = 154830)。