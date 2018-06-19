---
title: 清单： 从到另一个应用程序导出绑定 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 152924e6-da64-4db9-a852-bdb4e79687fb
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df60a6fd1b266403a5c43b5f76bf7594cad4f41a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299805"
---
# <a name="checklist-exporting-bindings-from-one-application-to-another"></a>清单： 导出绑定到另一个应用程序
本主题介绍在传输到另一个应用程序在开发或生产环境中的一个应用程序的绑定所涉及的步骤。 此过程是类似于部署使用.msi 文件的应用程序的过程。 但是，在部署使用.msi 文件的应用程序时，进程将自动创建应用程序。 当你从一个应用程序到另一个传输绑定时，另一方面，目标应用程序必须已存在。  
  
|步骤|参考|  
|-----------|---------------|  
|确保您具有执行导出操作的适当权限。|[用于管理应用程序的权限](../technical-guides/permissions-for-managing-an-application.md)|  
|创建要导入到的应用程序绑定的目标应用程序。|-   [创建应用程序](../technical-guides/creating-an-application.md)<br />-"创建 BizTalk 应用程序"部分[部署应用程序的最佳做法](../technical-guides/best-practices-for-deploying-an-application.md)|  
|导出到绑定文件的源应用程序的绑定。|-   [如何导出绑定到绑定文件](../technical-guides/how-to-export-bindings-to-a-binding-file.md)<br />-"导出 BizTalk 应用程序"部分[部署应用程序的最佳做法](../technical-guides/best-practices-for-deploying-an-application.md)<br />-"导出 BizTalk 应用程序"部分[与部署的应用程序的已知问题](../technical-guides/known-issues-with-deploying-an-application.md)。|  
|导入到目标应用程序的绑定文件中的绑定。|-   [如何从绑定文件导入的绑定](../technical-guides/how-to-import-bindings-from-a-binding-file.md)<br />-"导入 BizTalk 应用程序"部分[部署应用程序的最佳做法](../technical-guides/best-practices-for-deploying-an-application.md)<br />-"导入 BizTalk 应用程序"部分[与部署的应用程序的已知问题](../technical-guides/known-issues-with-deploying-an-application.md)。|