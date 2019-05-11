---
title: 清单：更新的程序集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5afcb78a-333b-46ff-8681-42362ce5aaad
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84cf2efe1d1115ed4b7c8ab50692db6f8d430482
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242553"
---
# <a name="checklist-updating-an-assembly"></a>清单：更新的程序集
以下清单描述了更新已部署的应用程序中的一个或多个项目，然后重新部署应用程序的过程。  
  
> [!NOTE]  
>  如果你不能计划停机时间或有不能以非常长时间运行实例，更新使用的并行版本控制。  
  
|步骤|参考|  
|-----------|---------------|  
|查看有关更新的应用程序中的项目的重要注意事项。|-   [有关更新应用程序的重要注意事项](http://go.microsoft.com/fwlink/?LinkId=154823)(http://go.microsoft.com/fwlink/?LinkId=154823)。<br />-   [更新应用程序的最佳实践](../technical-guides/best-practices-for-updating-applications.md)|  
|请确保您具有相应的权限来执行部署。|[管理应用程序的权限](../technical-guides/permissions-for-managing-an-application.md)|  
|对程序集，添加、 删除或重新配置所需的项目进行任何必要的更改。<br /><br /> 部署到 BizTalk 应用程序开发环境中的程序集从 Visual Studio。|-   [如何更新程序集](../technical-guides/how-to-update-an-assembly.md)<br />-   [更新某一项目](../technical-guides/updating-an-artifact.md)<br />-"正在更新项目"和"更新的程序集"的部分[更新应用程序的最佳实践](../technical-guides/best-practices-for-updating-applications.md)<br />-   [如何部署 BizTalk 程序集从 Visual Studio](http://go.microsoft.com/fwlink/?LinkId=154824) (http://go.microsoft.com/fwlink/?LinkId=154824)。|  
|测试所有新的或已更改的项目，确保可能依赖于新的或更改项目的所有项目也进行都测试。 **注意：** 在测试时，请务必考虑此应用程序和其他应用程序之间可能存在的依赖关系。|[BizTalk 应用程序部署的测试任务](http://go.microsoft.com/fwlink/?LinkId=154825)(http://go.microsoft.com/fwlink/?LinkId=154825)。|  
|在 BizTalk Server 管理控制台中，添加、 删除或重新配置中根据需要应用程序的项目。|-   [如何创建或添加项目](http://go.microsoft.com/fwlink/?LinkID=154724)(http://go.microsoft.com/fwlink/?LinkID=154724)。<br />-   [如何从应用程序中删除项目](http://go.microsoft.com/fwlink/?LinkID=154688)(http://go.microsoft.com/fwlink/?LinkID=154688)。<br />-   [管理项目](http://go.microsoft.com/fwlink/?LinkID=154725)(http://go.microsoft.com/fwlink/?LinkID=154725)。<br />-   [更新某一项目](../technical-guides/updating-an-artifact.md)<br />-"正在更新项目"一节[更新应用程序的最佳实践](../technical-guides/best-practices-for-updating-applications.md)。|  
|导出到.msi 文件包含新的或更改项目的应用程序。|-   [导出 BizTalk 应用程序、 绑定和策略](http://go.microsoft.com/fwlink/?LinkId=154826)(http://go.microsoft.com/fwlink/?LinkId=154826)。<br />-   [如何导出到.msi 文件的应用程序](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-"导出 BizTalk 应用程序"一节[部署应用程序的最佳做法](../technical-guides/best-practices-for-deploying-an-application.md)。|  
|如果该更新会影响应用程序在运行，计划停机时间，并停止你想要更新的应用程序。|-   [如何启动和停止 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkID=154729)(http://go.microsoft.com/fwlink/?LinkID=154729)。<br />-"启动或停止应用程序"部分[更新应用程序的最佳实践](../technical-guides/best-practices-for-updating-applications.md)。|  
|更改或更新项目从.msi 文件导入你想要更新的应用程序安装应用程序。 **注意：** 更新 BizTalk 程序集时，应停止并取消登记之前从.msi 文件导入的项目。 应重新登记，并从.msi 文件导入后启动 BizTalk 项目。|-   [如何导入 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkId=154827)(http://go.microsoft.com/fwlink/?LinkId=154827)。<br />-   [如何从某一.msi 文件导入应用程序](../technical-guides/how-to-import-an-application-from-an-msi-file.md)<br />-"导入 BizTalk 应用程序"一节[部署应用程序的最佳做法](../technical-guides/best-practices-for-deploying-an-application.md)。<br />-   [如何安装 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkID=154728)(http://go.microsoft.com/fwlink/?LinkID=154728)。<br />-   [如何将程序集安装到 GAC 中](http://go.microsoft.com/fwlink/?LinkId=154828)(http://go.microsoft.com/fwlink/?LinkId=154828)。|  
|启动应用程序，继续执行发布消息。 重新启动所有 BizTalk 主机实例。|-   [如何启动和停止 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkID=154729)(http://go.microsoft.com/fwlink/?LinkID=154729)。|  
|包含业务流程导入程序集后，如果应用程序向其导入它已包含具有相同的名称、 公钥标记和版本的程序集，停止和启动该业务流程将主机的主机实例绑定。 这可确保 BizTalk Server 使用程序集的新版本。|-   [如何停止主机实例](http://go.microsoft.com/fwlink/?LinkId=154829)(http://go.microsoft.com/fwlink/?LinkId=154829)。<br />-   [如何启动主机实例](http://go.microsoft.com/fwlink/?LinkId=154830)(http://go.microsoft.com/fwlink/?LinkId=154830)。|