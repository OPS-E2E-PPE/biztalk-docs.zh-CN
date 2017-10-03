---
title: "如何导出为.msi 文件的应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b7179e86-aa55-426b-a0db-19229ca5625a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 600118718585401d9ba6c3158b6510af55c53e74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-export-an-application-to-an-msi-file"></a>如何导出为.msi 文件的应用程序
可以使用导出 MSI 文件向导或 BTSTask 将导出到.msi 文件将用于将应用程序导入新的 BizTalk 组的应用程序项目。 此过程还会将运行它的计算机上安装应用程序。  
  
## <a name="exporting-application-bindings-in-an-msi-file"></a>导出程序.msi 文件中的应用程序绑定  
 在导出到.msi 文件的应用程序时，你选择要导出哪些资源。 这些资源可以包括所有数据或已部署的程序集的子集或绑定所提供的导出。  
  
 若要更加轻松地恢复到你的开发环境的应用程序导入一次更高版本进行更改或添加内容，你可能想要导出每个应用程序的绑定，然后将其添加回应用程序。 当设置为"BiztalkBinding"的资源类型时，你可以将其他绑定文件添加到.msi 文件。 对于你添加每个绑定文件，必须指定绑定应该应用到的环境名称 （文本字段）。 然后在导入时，你将需要选择目前导环境名称。 如果这些内容匹配，则绑定文件将应用到目标组。 你还可以指定添加的绑定文件，这将导致绑定无条件地应用于所有环境的集没有环境名称。  
  
 使用.msi 文件自动执行什么可以否则大设置的手动任务。 在生产环境中，你可以更加轻松地部署到多个 BizTalk 组程序集的传输以及程序集的程序集的绑定。 如果你的应用程序包含大量的项目，你可以将某些项目导出到一个 Windows Installer 包和某些为一个或多个其他 Windows Installer 包。  
  
 导出应用程序，时应考虑一些要点。 例如，您可能会将导出所有应用程序中的项目或你想要添加或更新项目。 如果导出文件项目，请确保它是你想要在应用程序中使用的版本。 多这样的点以及有关导出到.msi 文件 BizTalk 应用程序的详细信息，请参阅[how to Export BizTalk 应用程序如何](http://go.microsoft.com/fwlink/?LinkID=154848)(http://go.microsoft.com/fwlink/?LinkID=154848)。