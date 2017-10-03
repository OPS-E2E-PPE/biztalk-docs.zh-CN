---
title: "清单： 更新程序集 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5afcb78a-333b-46ff-8681-42362ce5aaad
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9b20aa7d1b0b901176f090ab7636ef0b3eccfa9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-updating-an-assembly"></a>清单： 更新程序集
以下清单描述更新已部署的应用程序中的一个或多个项目，然后重新部署应用程序的过程。  
  
> [!NOTE]  
>  如果不能计划停机时间或具有不能以很长时间运行实例，更新使用的并行版本控制。  
  
|步骤|参考|  
|-----------|---------------|  
|查看有关更新应用程序中的项目的重要注意事项。|-   [更新应用程序的重要注意事项](http://go.microsoft.com/fwlink/?LinkId=154823)(http://go.microsoft.com/fwlink/?LinkId=154823)。<br />-   [更新应用程序的最佳做法](../technical-guides/best-practices-for-updating-applications.md)|  
|确保你具有适当的权限执行部署。|[用于管理应用程序的权限](../technical-guides/permissions-for-managing-an-application.md)|  
|你的程序集，添加、 删除或重新配置所需的项目进行任何必要的更改。<br /><br /> 将部署到 BizTalk 应用程序在开发环境中的程序集从 Visual Studio。|-   [如何更新的程序集](../technical-guides/how-to-update-an-assembly.md)<br />-   [更新某个项目](../technical-guides/updating-an-artifact.md)<br />-"更新某个项目"和"更新程序集"部分的[更新应用程序的最佳实践](../technical-guides/best-practices-for-updating-applications.md)<br />-   [如何部署 BizTalk 程序集，从 Visual Studio](http://go.microsoft.com/fwlink/?LinkId=154824) (http://go.microsoft.com/fwlink/?LinkId=154824)。|  
|测试所有新的或更改的项目，确保也可能取决于新的或更改项目的所有项目得到了都测试。 **注意：**测试时，请务必考虑此应用程序和其他应用程序之间可能存在的依赖关系。|[BizTalk 应用程序部署为测试任务，](http://go.microsoft.com/fwlink/?LinkId=154825) (http://go.microsoft.com/fwlink/?LinkId=154825)。|  
|在 BizTalk Server 管理控制台中，添加、 删除或重新配置在根据需要应用程序中的项目。|-   [如何创建或添加项目](http://go.microsoft.com/fwlink/?LinkID=154724)(http://go.microsoft.com/fwlink/?LinkID=154724)。<br />-   [如何从应用程序中删除项目](http://go.microsoft.com/fwlink/?LinkID=154688)(http://go.microsoft.com/fwlink/?LinkID=154688)。<br />-   [管理项目](http://go.microsoft.com/fwlink/?LinkID=154725)(http://go.microsoft.com/fwlink/?LinkID=154725)。<br />-   [更新某个项目](../technical-guides/updating-an-artifact.md)<br />-"更新某个项目"部分[更新应用程序的最佳实践](../technical-guides/best-practices-for-updating-applications.md)。|  
|导出到.msi 文件中包含新的或更改项目的应用程序。|-   [导出 BizTalk 应用程序、 绑定和策略](http://go.microsoft.com/fwlink/?LinkId=154826)(http://go.microsoft.com/fwlink/?LinkId=154826)。<br />-   [如何导出为.msi 文件的应用程序](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-"导出 BizTalk 应用程序"部分[部署应用程序的最佳做法](../technical-guides/best-practices-for-deploying-an-application.md)。|  
|如果更新将会妨碍应用程序运行，计划停机时间，并且停止你想要更新应用程序。|-   [如何启动和停止 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkID=154729)(http://go.microsoft.com/fwlink/?LinkID=154729)。<br />-"启动或停止应用程序"部分[更新应用程序的最佳实践](../technical-guides/best-practices-for-updating-applications.md)。|  
|更改或更新项目从.msi 文件导入的应用程序想要更新，安装应用程序。 **注意：**更新 BizTalk 程序集时，你应停止并取消项目登记在导入从.msi 文件之前。 你应重新登记，然后启动 BizTalk 项目，在导入从.msi 之后。|-   [如何导入 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkId=154827)(http://go.microsoft.com/fwlink/?LinkId=154827)。<br />-   [如何从.msi 文件导入应用程序](../technical-guides/how-to-import-an-application-from-an-msi-file.md)<br />-"导入 BizTalk 应用程序"部分[部署应用程序的最佳做法](../technical-guides/best-practices-for-deploying-an-application.md)。<br />-   [如何安装 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkID=154728)(http://go.microsoft.com/fwlink/?LinkID=154728)。<br />-   [如何将程序集安装在 GAC 中](http://go.microsoft.com/fwlink/?LinkId=154828)(http://go.microsoft.com/fwlink/?LinkId=154828)。|  
|启动应用程序，恢复消息发布。 重新启动所有 BizTalk 主机实例。|-   [如何启动和停止 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkID=154729)(http://go.microsoft.com/fwlink/?LinkID=154729)。|  
|在导入程序集后包含业务流程，如果应用程序到你要导入它已包含具有相同名称、 公钥标记和版本的程序集，停止和启动到的业务流程的主机的主机实例绑定。 这可确保新版本的程序集由 BizTalk Server。|-   [如何停止主机实例](http://go.microsoft.com/fwlink/?LinkId=154829)(http://go.microsoft.com/fwlink/?LinkId=154829)。<br />-   [如何启动的主机实例](http://go.microsoft.com/fwlink/?LinkId=154830)(http://go.microsoft.com/fwlink/?LinkId=154830)。|