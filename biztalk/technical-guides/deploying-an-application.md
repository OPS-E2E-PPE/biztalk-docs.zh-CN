---
title: 部署应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04bb4496-b1e9-400b-a849-a355381849ff
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61bc0e446e635fd4111804f7160651df6492a60c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22300413"
---
# <a name="deploying-an-application"></a>部署应用程序
部署是逻辑分布的应用程序项目，以确保所有必需的组件可供需要它们的系统。 这些项目包括 BizTalk Server 程序集、.NET 程序集、 架构、 地图、 绑定、 业务规则和证书。 可以利用 BizTalk 应用程序，以帮助推出到其他计算机 （时传输到另一个环境的应用程序） 添加到组或用于过渡的项目。  
  
 有多种方法来部署 BizTalk 项目，例如将其导入应用程序的一部分使用部署向导 （从.msi 文件），将其导入使用 BTSTask.exe、 从 Visual Studio 中，部署或使用 MSBuild。 如果将其导入使用 BTSTask.exe 或者将它们部署从 Visual Studio 中，你可以指定应用程序可以将其部署到，也可以将应用程序名称保留为空，这种情况下它们将部署到默认应用程序。  
  
## <a name="deploying-by-using-an-msi-file"></a>使用.msi 文件部署  
 与 BizTalk Server 中，可以将其导出到.msi 文件来部署应用程序和其项目。 (有关应用程序和项目的详细信息，请参阅[BizTalk 应用程序是什么？](http://go.microsoft.com/fwlink/?LinkId=154994) (http://go.microsoft.com/fwlink/?LinkId=154994)。 BizTalk 应用程序部署涉及将应用程序项目导入 BizTalk 管理数据库，以及在组的成员的每台计算机上安装项目。 将部署到.msi 文件序列化的应用程序项目的所有到一个包中。 这可通过执行某一导出操作从管理控制台或从命令行使用 BTSTask.exe 执行。 .Msi 文件之后，您可以将所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]程序集到 BizTalk 管理组的数据库，或运行指定在导入时间运行的脚本。 这可通过使用 Microsoft 管理控制台 (MMC) 和执行导入操作的.msi 文件 （或通过导入操作从 BTSTASK 命令行）。 导入操作的.msi 文件的创建目标 BizTalk 应用程序。  
  
 使用.msi 文件时，你可以部署一台计算机上的应用程序，以便所有 BizTalk Server 程序集和依赖程序集都存储在计算机上的全局程序集缓存中。 计算机然后具有所有需要用于运行时二进制文件。 此操作，也可以推出解决方案的一部分，Web 服务或将特定于计算机的更改应用的脚本。 通过执行.msi 文件执行此操作。 你可以执行此操作运行是相关的 BizTalk 组的成员的 BizTalk Server 每台计算机上。 你可以使用.msi 文件添加到组的新服务器上安装应用程序。  
  
 如果你要迁移到新的组 BizTalk 应用程序，你需要在新的组中的所有服务器上运行.msi 安装。 你需要导入组一次的.msi 文件。 执行操作时，应用程序和其内容的新组中的所有运行时计算机上安装，然后还注册与组的 BizTalk 管理数据库。 你还可以将多个绑定文件添加到.msi 文件，除了隐式绑定。 每个其他绑定文件可能与"环境"。 当多个绑定文件在部署过程与 BizTalk 应用程序相关联时，你可以选择要使用哪些绑定文件到你要部署基于环境 （生产、 临时或测试）。  
  
 你可以使用脚本的.msi 文件以自定义的服务器 （安装操作） 或组 （导入操作）。 有关使用.msi 文件的脚本的信息的详细信息，请参阅[使用自定义应用程序部署到的前期和后期处理脚本](http://go.microsoft.com/fwlink/?LinkId=154995)(http://go.microsoft.com/fwlink/?LinkId=154995)。  
  
 部署应用程序的步骤清单，请参阅[清单： 部署应用程序](../technical-guides/checklist-deploying-an-application.md)。  
  
## <a name="exporting-an-applications-bindings-by-using-a-binding-file"></a>通过绑定文件导出应用程序的绑定  
 与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，你可以导出到绑定文件，应用程序的绑定，然后这些绑定从文件导入绑定到另一个应用程序。 若要执行此操作，必须已存在目标应用程序;导入过程不创建应用程序。 绑定文件是一个包含所有项目的应用程序、 组中，或程序集的绑定的 XML 文件。 你还可以导出为 BizTalk 组，所有绑定或 BizTalk 程序集的绑定。 有关使用绑定的详细信息，请参阅[如何导出绑定到绑定文件](../technical-guides/how-to-export-bindings-to-a-binding-file.md)和[如何从绑定文件导入绑定](../technical-guides/how-to-import-bindings-from-a-binding-file.md)。  
  
 此外，你还可以将绑定文件作为资源添加到.msi 文件 有关将绑定文件添加为资源的详细信息，请参阅[如何导出应用程序的.msi 文件](../technical-guides/how-to-export-an-application-to-an-msi-file.md)。  
  
 有关应用程序部署的详细信息一般情况下，请参阅[了解 BizTalk 应用程序部署和管理](http://go.microsoft.com/fwlink/?LinkId=154996)(http://go.microsoft.com/fwlink/?LinkId=154996)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [部署应用程序的最佳做法](../technical-guides/best-practices-for-deploying-an-application.md)  
  
-   [部署应用程序的已知的问题](../technical-guides/known-issues-with-deploying-an-application.md)  
  
-   [用于管理应用程序的权限](../technical-guides/permissions-for-managing-an-application.md)  
  
-   [在应用程序必须是唯一的项目](../technical-guides/artifacts-that-must-be-unique-in-an-application.md)  
  
-   [部署和导出应用程序](../technical-guides/deploying-and-exporting-an-application.md)