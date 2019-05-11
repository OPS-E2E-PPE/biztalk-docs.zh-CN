---
title: 清单：将应用程序部署 |Microsoft Docs
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
ms.openlocfilehash: 7a66c63237e09431ce1a9e8c711551e411ea20e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401824"
---
# <a name="checklist-deploying-an-application"></a>清单：将应用程序部署
本主题介绍部署 BizTalk 应用程序和其在生产环境中的项目时所涉及的步骤。 它演示了如何开发环境中部署应用程序，将其导出到.msi 文件，然后将其导入.msi 文件从在生产环境。  
  
 应用程序部署包含应用程序导入到组并在组中的单个服务器 （主机实例） 上安装应用程序。 有关导入和安装应用程序的详细信息，请参阅[如何从一个.msi 文件导入应用程序](../technical-guides/how-to-import-an-application-from-an-msi-file.md)。  
  
 有关应用程序部署的详细信息，请参阅[应用程序部署过程](http://go.microsoft.com/fwlink/p/?LinkId=154716)(http://go.microsoft.com/fwlink/p/?LinkId=154716)。  
  
|步骤|参考|  
|-----------|---------------|  
|请确保有适当的权限来执行部署。|[管理应用程序的权限](../technical-guides/permissions-for-managing-an-application.md)|  
|Visual Studio 中的部署属性设置为 BizTalk Server 解决方案，包括程序集将部署到的应用程序中的每个项目。<br /><br /> 部署 （或重新部署） 到开发环境中的 BizTalk 应用程序所需的 BizTalk Server 程序集。|-   [如何在 Visual Studio 中设置部署属性](http://go.microsoft.com/fwlink/p/?LinkId=154718)(http://go.microsoft.com/fwlink/p/?LinkId=154718)。<br />-   [部署 BizTalk 程序集从 Visual Studio 到 BizTalk 应用程序](http://go.microsoft.com/fwlink/p/?LinkId=154719)(http://go.microsoft.com/fwlink/p/?LinkId=154719)。<br />-   [如何重新部署 BizTalk 程序集从 Visual Studio](http://go.microsoft.com/fwlink/p/?LinkId=154720) (http://go.microsoft.com/fwlink/p/?LinkId=154720)。<br />-   [部署程序集](../technical-guides/deploying-an-assembly.md)<br />-"部署 BizTalk 应用程序"、"创建 BizTalk 应用程序"和"部署 BizTalk 程序集"的部分[部署应用程序的最佳做法](http://msdn.microsoft.com/library/gg634504.aspx)。<br />-"部署 BizTalk 应用程序"部分[部署应用程序的已知问题](../technical-guides/known-issues-with-deploying-an-application.md)。|  
|将项目添加到 BizTalk 应用程序并在开发环境中配置的项目。<br /><br /> 这可能包括项目分解到多个 BizTalk 应用程序。|-   [如何创建或添加项目](http://go.microsoft.com/fwlink/p/?LinkId=154724)(http://go.microsoft.com/fwlink/p/?LinkId=154724)。<br />-   [管理项目](http://go.microsoft.com/fwlink/p/?LinkId=154725)(http://go.microsoft.com/fwlink/p/?LinkId=154725)。<br />-   [绑定文件和应用程序部署](http://go.microsoft.com/fwlink/p/?LinkId=154726)(http://go.microsoft.com/fwlink/p/?LinkId=154726)。<br />-   [将项目添加到应用程序](../technical-guides/adding-artifacts-to-an-application.md)<br />-"将项目添加到 BizTalk 应用程序"一节[部署应用程序的最佳做法](http://msdn.microsoft.com/library/gg634504.aspx)。<br />-"将项目添加到 BizTalk 应用程序"一节[部署应用程序的已知问题](../technical-guides/known-issues-with-deploying-an-application.md)。|  
|导出到.msi 文件在开发环境中的 BizTalk 应用程序。|-   [如何导出到.msi 文件的应用程序](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-"导出 BizTalk 应用程序"一节[部署应用程序的最佳做法](http://msdn.microsoft.com/library/gg634504.aspx)。<br />-"导出 BizTalk 应用程序"一节[部署应用程序的已知问题](../technical-guides/known-issues-with-deploying-an-application.md)。|  
|导入.msi 文件从在生产环境的 BizTalk 应用程序。 （此操作包括应用程序导入到组和应用程序包含基于文件的项目，如果在组中的每个服务器上安装应用程序。）|-   [如何导出到.msi 文件的应用程序](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-   [如何安装应用程序](http://go.microsoft.com/fwlink/p/?LinkId=154728)(http://go.microsoft.com/fwlink/p/?LinkId=154728)。<br />-"导入 BizTalk 应用程序"部分中的[部署应用程序的最佳做法](http://msdn.microsoft.com/library/gg634504.aspx)<br />-"导入 BizTalk 应用程序"部分中的[部署应用程序的已知问题](../technical-guides/known-issues-with-deploying-an-application.md)|  
|在生产环境中请对 BizTalk 应用程序做任何进一步修改，使其在该环境，如更改端口配置中运行。 如果这样做，将导出到.msi 文件的应用程序。|-   [如何导出到.msi 文件的应用程序](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-   [创建和修改 BizTalk 应用程序](http://go.microsoft.com/fwlink/p/?LinkId=154727)(http://go.microsoft.com/fwlink/p/?LinkId=154727)。<br />-   [如何将绑定文件添加到应用程序 1](../technical-guides/how-to-add-a-binding-file-to-an-application1.md)<br />-"导出 BizTalk 应用程序"部分中的[部署应用程序的最佳做法](http://msdn.microsoft.com/library/gg634504.aspx)<br />-"导出 BizTalk 应用程序"部分中的[部署应用程序的已知问题](../technical-guides/known-issues-with-deploying-an-application.md)|  
|如果你在生产环境中进行了任何其他修改的 BizTalk 应用程序，安装从.msi 文件的 BizTalk 应用程序到将运行它在生产环境中的任何其他计算机。<br /><br /> 此外，应用程序导入你想要将其，部署的任何其他 BizTalk 组，如果应用程序包含基于文件的项目，这些组中的服务器上安装应用程序。|-   [如何安装 BizTalk 应用程序](http://go.microsoft.com/fwlink/p/?LinkId=154728)(http://go.microsoft.com/fwlink/p/?LinkId=154728)。<br />-   [如何从某一.msi 文件导入应用程序](../technical-guides/how-to-import-an-application-from-an-msi-file.md)<br />-"导入 BizTalk 应用程序"部分中的[部署应用程序的最佳做法](http://msdn.microsoft.com/library/gg634504.aspx)<br />-"导入 BizTalk 应用程序"部分中的[部署应用程序的已知问题](../technical-guides/known-issues-with-deploying-an-application.md)|  
|从 BizTalk Server 管理控制台在生产环境中启动 BizTalk 应用程序并验证它正常。|-   [如何启动和停止 BizTalk 应用程序](http://go.microsoft.com/fwlink/p/?LinkId=154729)(http://go.microsoft.com/fwlink/p/?LinkId=154729)。<br />-   [测试的应用程序](../technical-guides/testing-an-application.md)|  
  
## <a name="see-also"></a>请参阅  
 [部署程序集](../technical-guides/deploying-an-assembly.md)   
 [将项目添加到应用程序](../technical-guides/adding-artifacts-to-an-application.md)   
 [如何导出到.msi 文件的应用程序](../technical-guides/how-to-export-an-application-to-an-msi-file.md)   
 [如何将绑定导出到绑定文件](../technical-guides/how-to-export-bindings-to-a-binding-file.md)   
 [如何从某一.msi 文件导入应用程序](../technical-guides/how-to-import-an-application-from-an-msi-file.md)   
 [如何安装应用程序](../technical-guides/how-to-install-an-application.md)   
 [如何从绑定文件导入绑定](../technical-guides/how-to-import-bindings-from-a-binding-file.md)