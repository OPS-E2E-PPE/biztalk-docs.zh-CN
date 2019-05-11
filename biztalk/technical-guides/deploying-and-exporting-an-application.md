---
title: 部署和导出应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4106a0a7-878d-4052-8eca-02d546233048
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70f3638d3679fd133289a36df74efec1fd020e7f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305831"
---
# <a name="deploying-and-exporting-an-application"></a>部署和导出应用程序
本部分包含有关如何在部署 BizTalk 应用程序执行所涉及的步骤的详细的信息。 在本部分中的主题支持以下检查表：  
  
- [清单：将应用程序部署](../technical-guides/checklist-deploying-an-application.md)，其中说明了如何开发环境中部署应用程序，将其导出到.msi 文件中，然后将其导入生产环境中从.msi 文件。  
  
- [清单：将绑定导出到另一个应用程序从](../technical-guides/checklist-exporting-bindings-from-one-application-to-another.md)，其中说明了如何导出到另一个应用程序中的应用程序中的绑定用于开发或生产环境。  
  
  可以使用以下工具来部署和管理 BizTalk 应用程序：  
  
|                             Tool                             |                                                                                                                                                                                                                                                                                                                                                                                                                                 改用                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|--------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|            BizTalk Server 管理控制台             | 此图形用户界面，可以执行的所有部署和管理 BizTalk 应用程序，包括以下操作：<br /><br /> -启动导入、 安装和导出向导<br />-添加和删除应用程序项目，以及进行其他修改应用程序<br />生成 BizTalk 应用程序的 BizTalk Server.msi 文件<br />-从.msi 文件安装到的计算机上的应用程序或应用程序从.msi 文件导入到其他 BizTalk 组<br />-导入的绑定应用程序从绑定文件<br /><br /> 有关在管理控制台的详细信息，请参阅[使用 BizTalk Server 管理控制台](http://go.microsoft.com/fwlink/?LinkID=154689)(<http://go.microsoft.com/fwlink/?LinkID=154689>)。 |
|                  BTSTask 命令行工具                   |                                                                                                                                                                                                                                                                                                  您可以从命令行执行许多应用程序管理任务。 有关命令行工具的详细信息，请参阅[BTSTask 命令行参考](http://go.microsoft.com/fwlink/?LinkId=155003)(<http://go.microsoft.com/fwlink/?LinkId=155003>)。                                                                                                                                                                                                                                                                                                   |
|              脚本和可编程 Api              |                                                                                                                                                                                                                                                           可以使用 Microsoft Windows Management Instrumentation (WMI) 或 BizTalk 浏览器对象模型来创建和运行自动执行许多应用程序管理任务的脚本。 有关脚本的详细信息，请参阅[WMI 类引用](http://go.microsoft.com/fwlink/?LinkId=155004)(<http://go.microsoft.com/fwlink/?LinkId=155004>)。                                                                                                                                                                                                                                                           |
| [!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)] |                                                                                                                                                                                                可以在 Visual Studio 中创建 BizTalk 程序集、 使用部署命令自动将它们部署到 BizTalk 应用程序，并使用 BizTalk 浏览器配置从 Visual Studio 中的应用程序项目。 有关 Visual Studio 中使用的详细信息，请参阅[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](http://go.microsoft.com/fwlink/?LinkID=154719)(<http://go.microsoft.com/fwlink/?LinkID=154719>)。                                                                                                                                                                                                |
  
## <a name="in-this-section"></a>本节内容  
  
-   [创建应用程序](../technical-guides/creating-an-application.md)  
  
-   [部署程序集](../technical-guides/deploying-an-assembly.md)  
  
-   [将项目添加到应用程序](../technical-guides/adding-artifacts-to-an-application.md)  
  
-   [如何将应用程序导出到 .msi 文件](../technical-guides/how-to-export-an-application-to-an-msi-file.md)  
  
-   [如何将绑定导出到绑定文件](../technical-guides/how-to-export-bindings-to-a-binding-file.md)  
  
-   [如何将绑定文件添加到应用程序 1](../technical-guides/how-to-add-a-binding-file-to-an-application1.md)  
  
-   [如何从 .msi 文件导入应用程序](../technical-guides/how-to-import-an-application-from-an-msi-file.md)  
  
-   [如何安装应用程序](../technical-guides/how-to-install-an-application.md)  
  
-   [如何从绑定文件导入绑定](../technical-guides/how-to-import-bindings-from-a-binding-file.md)  
  
-   [测试应用程序](../technical-guides/testing-an-application.md)  
  
-   [如何将引用添加到应用程序](../technical-guides/how-to-add-a-reference-to-an-application.md)