---
title: 将应用程序部署 |Microsoft Docs
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
ms.openlocfilehash: c2fb0faec11638f48f0b776988a555c34c6fc62a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002814"
---
# <a name="deploying-an-application"></a>将应用程序部署
部署是应用程序项目，以确保所有必需的组件可供需要它们的系统的物流分布。 这些项目包括 BizTalk Server 程序集、.NET 程序集、 架构、 映射、 绑定、 业务规则和证书。 可以利用 BizTalk 应用程序，以帮助向其他计算机 （时传输到另一个环境的应用程序） 添加到组或用于过渡推出项目。  
  
 有多种方法来部署 BizTalk 项目，例如使用导入它们作为应用程序的一部分部署向导 （从.msi 文件），将其导入使用 BTSTask.exe、 从 Visual Studio 中，部署或使用 MSBuild。 如果将其导入使用 BTSTask.exe 或者将它们部署在 Visual Studio 中，可以指定应用程序将它们部署到，也可以将应用程序名称保留为空，这种情况下它们将部署到默认应用程序。  
  
## <a name="deploying-by-using-an-msi-file"></a>使用某一.msi 文件部署  
 使用 BizTalk Server 中，可以将其导出到某一.msi 文件来部署应用程序和其项目。 (有关应用程序和项目的详细信息，请参阅[BizTalk 应用程序是什么？](http://go.microsoft.com/fwlink/?LinkId=154994) (<http://go.microsoft.com/fwlink/?LinkId=154994>). BizTalk 应用程序的部署涉及到将应用程序项目导入到 BizTalk 管理数据库，以及是组的成员每台计算机上安装项目。 部署到某一.msi 文件序列化的所有应用程序项目打包到一个包。 这可以通过执行导出操作从管理控制台或使用 BTSTask.exe 从命令行执行。 某一.msi 文件后，可以部署所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]程序集到 BizTalk 管理数据库的组或运行指定要在导入时运行脚本。 这是通过使用 Microsoft 管理控制台 (MMC) 并执行导入操作的.msi 文件 （或通过导入操作从 BTSTASK 命令行）。 .Msi 文件导入操作创建目标 BizTalk 应用程序。  
  
 使用.msi 文件中，可以部署一台计算机上的应用程序，以便所有 BizTalk Server 程序集和依赖程序集都存储在计算机上的全局程序集缓存中。 计算机然后了所有运行时为所需的二进制文件。 此操作，还可以推出解决方案的一部分的 Web 服务或应用特定于计算机的更改的脚本。 通过执行.msi 文件来执行此操作。 您可以执行此操作运行 BizTalk Server 相关的 BizTalk 组的成员每台计算机上。 此外可以使用某一.msi 文件添加到组的新服务器上安装应用程序。  
  
 如果要迁移到新的组的 BizTalk 应用程序，您需要在新组中的所有服务器上运行.msi 安装。 需要导入.msi 文件中的一次为组。 执行操作时，应用程序和其内容在新组中的所有运行时计算机上安装并已注册与组的 BizTalk 管理数据库。 此外可以将多个绑定文件添加到.msi 文件，除了隐式绑定。 每个其他绑定文件可以与"环境"相关联。 当多个绑定文件在部署过程中将 BizTalk 应用程序相关联时，可以选择要使用的绑定文件部署到基于环境 （生产、 临时或测试）。  
  
 使用.msi 文件中，可以使用脚本自定义的服务器 （安装操作） 或组 （导入操作）。 脚本中使用的.msi 文件的详细信息，请参阅[使用自定义应用程序部署到的前期和后期处理脚本](http://go.microsoft.com/fwlink/?LinkId=154995)(http://go.microsoft.com/fwlink/?LinkId=154995)。  
  
 部署应用程序的步骤清单，请参阅[清单： 部署应用程序](../technical-guides/checklist-deploying-an-application.md)。  
  
## <a name="exporting-an-applications-bindings-by-using-a-binding-file"></a>使用绑定文件导出应用程序的绑定  
 使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以导出到绑定文件中，应用程序的绑定，然后这些绑定从文件导入绑定到另一个应用程序。 若要执行此操作，必须已经存在目标应用程序;导入过程不创建应用程序。 绑定文件是包含在应用程序、 组或程序集的所有项目的绑定的 XML 文件。 此外可以导出的 BizTalk 组，所有绑定或 BizTalk 程序集的绑定。 有关使用绑定的详细信息，请参阅[如何导出到绑定文件的绑定](../technical-guides/how-to-export-bindings-to-a-binding-file.md)并[如何从绑定文件导入绑定](../technical-guides/how-to-import-bindings-from-a-binding-file.md)。  
  
 此外可以到某一.msi 文件作为资源添加绑定文件。 有关将绑定文件添加为资源的详细信息，请参阅[如何导出到.msi 文件的应用程序](../technical-guides/how-to-export-an-application-to-an-msi-file.md)。  
  
 详细了解应用程序部署在一般情况下，请参阅[了解 BizTalk 应用程序部署和管理](http://go.microsoft.com/fwlink/?LinkId=154996)(http://go.microsoft.com/fwlink/?LinkId=154996)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [部署应用程序的最佳做法](../technical-guides/best-practices-for-deploying-an-application.md)  
  
-   [部署应用程序过程中的已知问题](../technical-guides/known-issues-with-deploying-an-application.md)  
  
-   [管理应用程序的权限](../technical-guides/permissions-for-managing-an-application.md)  
  
-   [在应用程序中必须唯一的项目](../technical-guides/artifacts-that-must-be-unique-in-an-application.md)  
  
-   [部署和导出应用程序](../technical-guides/deploying-and-exporting-an-application.md)