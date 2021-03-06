---
title: 如何导出到.msi 文件的应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7179e86-aa55-426b-a0db-19229ca5625a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de4128fe004c8b28dedfb1ab7ac5c252e16ca38d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65320728"
---
# <a name="how-to-export-an-application-to-an-msi-file"></a>如何导出到.msi 文件的应用程序
可以使用导出 MSI 文件向导或 BTSTask 将应用程序项目导出到.msi 文件将用于该应用程序导入新的 BizTalk 组。 此过程还会将运行它的计算机上安装应用程序。  
  
## <a name="exporting-application-bindings-in-an-msi-file"></a>导出.msi 文件中的应用程序绑定  
 在导出到.msi 文件的应用程序时，您选择要导出哪些资源。 这些资源可以包含全部或部分的已部署的程序集或绑定所提供的导出。  
  
 若要更加轻松地返回到你的开发环境的应用程序导入在以后要进行更改或添加，可能想要导出的每个应用程序绑定，然后将其添加回应用程序。 当设置为"BiztalkBinding"的资源类型时，可以将其他绑定文件添加到某一.msi 文件。 对于你添加的每个绑定文件，必须指定绑定应应用于的环境名称 （文本字段）。 然后在导入时，您将需要选择目前导环境名称。 如果这些内容匹配，则会将绑定文件应用到目标组。 此外可以指定添加的绑定文件，这将导致的无条件地应用于所有环境的绑定集没有环境名称。  
  
 使用.msi 文件会自动将什么可以否则庞大的因此设置的手动任务。 在生产环境中，您可以轻松地部署到多个 BizTalk 组的程序集的传输以及该程序集的程序集的绑定。 如果你的应用程序包含大量的项目，可以将一些项目导出到一个 Windows Installer 程序包和一些到一个或多个其他 Windows 安装程序包。  
  
 同时导出该应用程序，则应考虑一些要点。 例如，您可能会将导出的所有应用程序中的项目或只想要添加或更新的项目。 如果将导出文件项目，请确保它是你想要在应用程序中使用的版本。 有关更多这样的点和有关导出到.msi 文件的 BizTalk 应用程序的详细信息，请参阅[如何导出 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkID=154848)(http://go.microsoft.com/fwlink/?LinkID=154848)。