---
title: 清单： 部署应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5e699ac3-7998-48d6-96b7-2f8f1a3d52e5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 713eef12a06cb8331faf39acede7c14143a45032
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299853"
---
# <a name="checklist-deploying-an-application"></a>清单： 部署应用程序
本主题介绍中部署 BizTalk 应用程序和其在生产环境中的项目所涉及的步骤。 它演示了如何部署应用程序在开发环境中的，将其导出到.msi 文件中，然后将其导入生产环境中的.msi 文件。  
  
 应用程序部署包含将应用程序导入一组和在组中的单个服务器 （主机实例） 上安装应用程序。 有关导入和安装应用程序的详细信息，请参阅[如何从一个.msi 文件导入应用程序](../technical-guides/how-to-import-an-application-from-an-msi-file.md)。  
  
 有关应用程序部署的详细信息，请参阅[应用程序部署过程](http://go.microsoft.com/fwlink/p/?LinkId=154716)(http://go.microsoft.com/fwlink/p/?LinkId=154716)。  
  
|步骤|参考|  
|-----------|---------------|  
|确保你具有适当的权限执行部署。|[用于管理应用程序的权限](../technical-guides/permissions-for-managing-an-application.md)|  
|BizTalk Server 解决方案，包括程序集将部署到应用程序中每个项目在 Visual Studio 中设置部署属性。<br /><br /> 部署 （或重新部署） 到 BizTalk 应用程序在开发环境中所需的 BizTalk Server 程序集。|-   [如何在 Visual Studio 中设置部署属性](http://go.microsoft.com/fwlink/p/?LinkId=154718)(http://go.microsoft.com/fwlink/p/?LinkId=154718)。<br />-   [部署到 BizTalk 应用程序程序集从 Visual Studio BizTalk](http://go.microsoft.com/fwlink/p/?LinkId=154719) (http://go.microsoft.com/fwlink/p/?LinkId=154719)。<br />-   [如何重新部署 BizTalk 程序集从 Visual Studio](http://go.microsoft.com/fwlink/p/?LinkId=154720) (http://go.microsoft.com/fwlink/p/?LinkId=154720)。<br />-   [部署程序集](../technical-guides/deploying-an-assembly.md)<br />-"部署 BizTalk 应用程序"、"创建 BizTalk 应用程序"和"部署 BizTalk 程序集"部分的[部署应用程序的最佳做法](http://msdn.microsoft.com/library/gg634504.aspx)。<br />-"部署 BizTalk 应用程序"部分[与部署的应用程序的已知问题](../technical-guides/known-issues-with-deploying-an-application.md)。|  
|将项目添加到 BizTalk 应用程序，并在开发环境中配置项目。<br /><br /> 这可能包括将项目分解为多个 BizTalk 应用程序。|-   [如何创建或添加项目](http://go.microsoft.com/fwlink/p/?LinkId=154724)(http://go.microsoft.com/fwlink/p/?LinkId=154724)。<br />-   [管理项目](http://go.microsoft.com/fwlink/p/?LinkId=154725)(http://go.microsoft.com/fwlink/p/?LinkId=154725)。<br />-   [绑定文件和应用程序部署](http://go.microsoft.com/fwlink/p/?LinkId=154726)(http://go.microsoft.com/fwlink/p/?LinkId=154726)。<br />-   [将项目添加到应用程序](../technical-guides/adding-artifacts-to-an-application.md)<br />-"将项目添加到 BizTalk 应用程序"部分[部署应用程序的最佳做法](http://msdn.microsoft.com/library/gg634504.aspx)。<br />-"将项目添加到 BizTalk 应用程序"部分[与部署的应用程序的已知问题](../technical-guides/known-issues-with-deploying-an-application.md)。|  
|导出到.msi 文件在开发环境中的 BizTalk 应用程序。|-   [如何导出为.msi 文件的应用程序](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-"导出 BizTalk 应用程序"部分[部署应用程序的最佳做法](http://msdn.microsoft.com/library/gg634504.aspx)。<br />-"导出 BizTalk 应用程序"部分[与部署的应用程序的已知问题](../technical-guides/known-issues-with-deploying-an-application.md)。|  
|导入的.msi 文件从生产环境的 BizTalk 应用程序。 （此操作将应用程序导入组和组成应用程序包括基于文件的项目，如果在组中的每个服务器上安装应用程序。）|-   [如何导出为.msi 文件的应用程序](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-   [如何安装应用程序](http://go.microsoft.com/fwlink/p/?LinkId=154728)(http://go.microsoft.com/fwlink/p/?LinkId=154728)。<br />-"导入 BizTalk 应用程序"部分[部署应用程序的最佳做法](http://msdn.microsoft.com/library/gg634504.aspx)<br />-"导入 BizTalk 应用程序"部分[与部署的应用程序的已知问题](../technical-guides/known-issues-with-deploying-an-application.md)|  
|使其运行在该环境中，例如更改端口配置，请在生产环境中进行 BizTalk 应用程序的其他任何修改。 如果这样做，将导出应用程序置于.msi 文件。|-   [如何导出为.msi 文件的应用程序](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-   [创建和修改 BizTalk 应用程序](http://go.microsoft.com/fwlink/p/?LinkId=154727)(http://go.microsoft.com/fwlink/p/?LinkId=154727)。<br />-   [如何将绑定文件添加到应用程序 1](../technical-guides/how-to-add-a-binding-file-to-an-application1.md)<br />-"导出 BizTalk 应用程序"部分[部署应用程序的最佳做法](http://msdn.microsoft.com/library/gg634504.aspx)<br />-"导出 BizTalk 应用程序"部分[与部署的应用程序的已知问题](../technical-guides/known-issues-with-deploying-an-application.md)|  
|如果你在生产环境中进行了任何其他修改 BizTalk 应用程序，安装.msi 文件从 BizTalk 应用程序到将运行该生产环境中的任何其他计算机。<br /><br /> 此外，将应用程序导入到你想要部署该环节，任何其他 BizTalk 组，如果应用程序包括基于文件的项目，在这些组中的服务器上安装应用程序。|-   [如何安装 BizTalk 应用程序](http://go.microsoft.com/fwlink/p/?LinkId=154728)(http://go.microsoft.com/fwlink/p/?LinkId=154728)。<br />-   [如何从.msi 文件导入应用程序](../technical-guides/how-to-import-an-application-from-an-msi-file.md)<br />-"导入 BizTalk 应用程序"部分[部署应用程序的最佳做法](http://msdn.microsoft.com/library/gg634504.aspx)<br />-"导入 BizTalk 应用程序"部分[与部署的应用程序的已知问题](../technical-guides/known-issues-with-deploying-an-application.md)|  
|从 BizTalk Server 管理控制台的生产环境中启动 BizTalk 应用程序并验证它正常。|-   [如何启动和停止 BizTalk 应用程序](http://go.microsoft.com/fwlink/p/?LinkId=154729)(http://go.microsoft.com/fwlink/p/?LinkId=154729)。<br />-   [测试应用程序](../technical-guides/testing-an-application.md)|  
  
## <a name="see-also"></a>另请参阅  
 [部署程序集](../technical-guides/deploying-an-assembly.md)   
 [将项目添加到应用程序](../technical-guides/adding-artifacts-to-an-application.md)   
 [如何导出为.msi 文件的应用程序](../technical-guides/how-to-export-an-application-to-an-msi-file.md)   
 [如何导出绑定到绑定文件](../technical-guides/how-to-export-bindings-to-a-binding-file.md)   
 [如何从.msi 文件导入应用程序](../technical-guides/how-to-import-an-application-from-an-msi-file.md)   
 [如何安装应用程序](../technical-guides/how-to-install-an-application.md)   
 [如何从绑定文件导入的绑定](../technical-guides/how-to-import-bindings-from-a-binding-file.md)