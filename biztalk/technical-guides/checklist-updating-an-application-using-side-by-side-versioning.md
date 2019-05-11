---
title: 清单：更新使用的并行版本控制的应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3adee8da-18d4-4b9e-a22e-148b90d18179
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9311dca6c14ea520dfbef35b603968b0c338b484
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242570"
---
# <a name="checklist-updating-an-application-using-side-by-side-versioning"></a>清单：更新使用的并行版本控制的应用程序
以下清单描述了部署的 BizTalk 应用程序将运行的同时更新的版本的过程与现有版本。  
  
 通过并行安装可以以增量方式推出应用程序升级。 您可以提供安装一部分的业务合作伙伴到最初，而不是所有合作伙伴在一次。 使用此方法使您可以继续运行现有应用程序服务尚未使用新版本直到您就可以完全将移动到新版本的用户。  
  
 将具有两个并行的应用程序以接收在两个不同的消息的接收位置。 因此，若要运行的并行应用程序必须要求这些贸易合作伙伴谁应使用应用程序的新版本发送到新的消息的接收位置，以便它们将由新版本进行处理。 这些贸易合作伙伴，应使用旧的版本应发送到上一个消息的接收位置。  
  
|步骤|参考|  
|-----------|---------------|  
|创建和实施版本控制策略。|在"版本管理"部分[更新应用程序的最佳实践](../technical-guides/best-practices-for-updating-applications.md)。|  
|对你想要部署到应用程序的新版本的项目进行任何必要的更改。|-   [如何创建或添加项目](http://go.microsoft.com/fwlink/?LinkID=154724)(http://go.microsoft.com/fwlink/?LinkID=154724)。<br />-   [管理项目](http://go.microsoft.com/fwlink/?LinkID=154725)(http://go.microsoft.com/fwlink/?LinkID=154725)。<br />-   [绑定文件和应用程序部署](http://go.microsoft.com/fwlink/?LinkID=154726)(http://go.microsoft.com/fwlink/?LinkID=154726)。<br />-   [将项目添加到应用程序](../technical-guides/adding-artifacts-to-an-application.md)|  
|递增每个程序集的版本号。|[如何更新程序集](../technical-guides/how-to-update-an-assembly.md)|  
|在解决方案 （设置目标应用程序和启用安装到全局程序集缓存 (GAC)） 中设置每个项目的部署属性。|[如何更新程序集](../technical-guides/how-to-update-an-assembly.md)|  
|部署包含到你的开发环境中的应用程序更改的程序集的解决方案。|-   [部署 BizTalk 程序集从 Visual Studio 到 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkID=154719)(http://go.microsoft.com/fwlink/?LinkID=154719)。<br />-   [如何重新部署 BizTalk 程序集从 Visual Studio](http://go.microsoft.com/fwlink/?LinkID=154720) (http://go.microsoft.com/fwlink/?LinkID=154720)。<br />-   [部署程序集](../technical-guides/deploying-an-assembly.md)|  
|创建一个新的接收端口和任何所需接收位置，指定您希望合作伙伴将消息发送到的新 Url。<br /><br /> 根据需要创建相应的发送端口。<br /><br /> 如有必要，绑定到新创建新的应用程序接收和发送端口和测试应用程序正常工作。|-   [如何创建接收端口](http://go.microsoft.com/fwlink/?LinkId=154843)(http://go.microsoft.com/fwlink/?LinkId=154843)。<br />-   [如何创建接收位置](http://go.microsoft.com/fwlink/?LinkId=154844)(http://go.microsoft.com/fwlink/?LinkId=154844)。<br />-   [如何创建发送端口](http://go.microsoft.com/fwlink/?LinkId=154845)(http://go.microsoft.com/fwlink/?LinkId=154845)。<br />-   [如何配置应用程序](http://go.microsoft.com/fwlink/?LinkId=154847)(http://go.microsoft.com/fwlink/?LinkId=154847)。|  
|从开发环境中导出到.msi 文件新的应用程序。|-   [如何导出 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkId=154848)(http://go.microsoft.com/fwlink/?LinkId=154848)。<br />-   [绑定文件和应用程序部署](http://go.microsoft.com/fwlink/?LinkID=154726)(http://go.microsoft.com/fwlink/?LinkID=154726)。<br />-   [如何导出到.msi 文件的应用程序](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-   [如何将绑定导出到绑定文件](../technical-guides/how-to-export-bindings-to-a-binding-file.md)|  
|应用程序.msi 文件导入生产环境中的 BizTalk 组。|-   [如何导入 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkId=154827)(http://go.microsoft.com/fwlink/?LinkId=154827)。<br />-   [如何安装 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkID=154728)(http://go.microsoft.com/fwlink/?LinkID=154728)。<br />-   [如何从某一.msi 文件导入应用程序](../technical-guides/how-to-import-an-application-from-an-msi-file.md)<br />-   [如何从绑定文件导入绑定](../technical-guides/how-to-import-bindings-from-a-binding-file.md)|  
|执行完整启动应用程序。|-   [如何启动和停止 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkID=154729)(http://go.microsoft.com/fwlink/?LinkID=154729)。<br />-   [BizTalk 应用程序部署的测试任务](http://go.microsoft.com/fwlink/?LinkId=154825)(http://go.microsoft.com/fwlink/?LinkId=154825)。|  
|通知你的合作伙伴，它们应开始将消息发送到新的 Url。 一旦他们执行此操作，应用程序开始为指定合作伙伴处理消息。|-|