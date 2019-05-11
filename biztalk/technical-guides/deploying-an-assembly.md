---
title: 部署程序集 |Microsoft Docs
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
ms.openlocfilehash: b4cbffe6b060e856288606aa89d8a00f08fd8a21
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305819"
---
# <a name="deploying-an-assembly"></a>部署程序集
部署程序集生成的程序集，并将其，以及业务流程、 管道、 架构和映射 （项目），它包含到本地 BizTalk 管理数据库导入。 最初，这是在开发环境。  
  
 部署还将程序集与您在 Visual Studio 中的项目属性中指定的 BizTalk 应用程序相关联。 部署解决方案后，可以查看和管理已部署的程序集和从其项目在 BizTalk Server 管理控制台内或通过使用 BTSTask 命令行工具。 可以管理的项目可以单独或组合在应用程序中。  
  
## <a name="deploying-an-assembly"></a>部署程序集  
 按以下方式，可以将程序集添加到应用程序：  
  
- 从 Visual Studio 环境内的应用程序部署的程序集  
  
- 手动将 BizTalk Server 程序集添加到 BizTalk Server 管理控制台中从应用程序  
  
- 使用脚本从命令行向应用程序添加 BizTalk 程序集  
  
- 从 BizTalk Server 管理控制台从其他应用程序移动 BizTalk Server 程序集  
  
  有关将程序集添加到应用程序的详细信息，请参阅[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](http://go.microsoft.com/fwlink/?LinkID=154719)(http://go.microsoft.com/fwlink/?LinkID=154719)。  
  
## <a name="redeploying-assemblies"></a>重新部署程序集  
 在过程中开发和调试您的 BizTalk 程序集，可能需要多次重新部署它们。 BizTalk Server 提供用于重新部署一个简单的机制。 如果不更改版本号的情况下，要重新部署程序集，可以使用重新部署属性。 BizTalk Server 将自动执行所有步骤才能重新部署您的程序集。  
  
 重新部署程序集的详细信息，请参阅[如何重新部署 BizTalk 程序集从 Visual Studio](http://go.microsoft.com/fwlink/?LinkID=154720) (http://go.microsoft.com/fwlink/?LinkID=154720)。  
  
### <a name="best-practices-for-redeploying-an-assembly"></a>重新部署程序集的最佳实践  
 **必须在 GAC 中安装新程序集**  
  
- 时重新部署程序集时，始终必须安装在全局程序集缓存 (GAC) 中的程序集的新版本。 重新部署它后，你可以执行此操作。 有关详细信息，请参阅[如何将程序集安装到 GAC 中](http://go.microsoft.com/fwlink/?LinkID=154828)(http://go.microsoft.com/fwlink/?LinkID=154828)。  
  
  **您应始终重新部署解决方案级别的依赖项时**  
  
- 如果在解决方案中，有多个程序集并在解决方案中的一个或多个程序集具有你想要重新部署的程序集的依赖项，则应重新部署您在解决方案级别的程序集。 这是因为 BizTalk Server 时重新部署项目级别的程序集，将停止、 取消登记、 取消绑定，并删除中的所有程序集是取决于此程序集或此程序集所依赖的项目。 BizTalk Server 不会执行附加步骤以部署、 绑定、 登记和启动这些项目。 当您重新部署整个解决方案时，但是，BizTalk Server 会自动编制取消部署和重新部署所有基于及其依赖项的解决方案中的项目所需的步骤。  
  
  **可能需要手动重新部署依存程序集**  
  
- BizTalk Server 通常取消部署依存程序集时取消部署程序集，但在以下情况下，您必须执行附加步骤以部署、 绑定和登记中每个依赖程序集后重新部署的程序集的项目程序集取决于：  
  
   如果重新部署项目级别的程序集，并且在同一解决方案中的另一个程序集依赖于它。  
  
   如果重新部署程序集级别的解决方案，但依赖程序集存在于另一种解决方案。  
  
  **必须重新启动主机实例**  
  
- 重新部署包含业务流程，而无需更改程序集版本号的程序集时，现有程序集将在 BizTalk 管理数据库中被覆盖。 此更改将生效之前，但是，必须重新启动该业务流程绑定到主机的每个主机实例。 可以指定本地计算机上的所有主机实例时自动重新都启动重新部署程序集的选项。  
  
   重新部署包含业务流程，而无需更改程序集版本号的程序集时，现有程序集将在 BizTalk 管理数据库中被覆盖。 此更改将生效之前，但是，必须重新启动该业务流程绑定到主机的每个主机实例。 可以指定本地计算机上的所有主机实例时自动重新都启动重新部署程序集的选项。 有关部署属性的详细信息，请参阅[如何在 Visual Studio 中设置部署属性](http://go.microsoft.com/fwlink/?LinkID=154718)(http://go.microsoft.com/fwlink/?LinkID=154718)。  
  
   您可以手动停止和启动每个主机实例。 有关停止和启动主机实例的详细信息，请参阅[如何停止主机实例](http://go.microsoft.com/fwlink/?LinkID=154829)(http://go.microsoft.com/fwlink/?LinkID=154829)并[如何启动主机实例](http://go.microsoft.com/fwlink/?LinkID=154830)(http://go.microsoft.com/fwlink/?LinkID=154830)。