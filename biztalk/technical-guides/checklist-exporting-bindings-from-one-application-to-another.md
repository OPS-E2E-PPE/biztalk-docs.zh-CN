---
title: 清单：将绑定导出到另一个应用程序从 |Microsoft Docs
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
ms.openlocfilehash: a7da1e88eb3745c60630827732ac92d167e4520b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401836"
---
# <a name="checklist-exporting-bindings-from-one-application-to-another"></a>清单：将绑定导出到另一个应用程序
本主题介绍在传输到其他应用程序开发或生产环境中的一个应用程序的绑定所涉及的步骤。 此过程是类似于使用某一.msi 文件部署应用程序的过程。 但是，在部署时使用某一.msi 文件的应用程序，则过程将自动创建应用程序。 如果从一个应用程序到另一个传输绑定，但是，目标应用程序必须已存在。  
  
|步骤|参考|  
|-----------|---------------|  
|确保具有执行导出操作的适当权限。|[管理应用程序的权限](../technical-guides/permissions-for-managing-an-application.md)|  
|创建要导入应用程序绑定到的目标应用程序。|-   [创建应用程序](../technical-guides/creating-an-application.md)<br />-"创建 BizTalk 应用程序"部分中的[部署应用程序的最佳做法](../technical-guides/best-practices-for-deploying-an-application.md)|  
|导出到绑定文件的源应用程序的绑定。|-   [如何将绑定导出到绑定文件](../technical-guides/how-to-export-bindings-to-a-binding-file.md)<br />-"导出 BizTalk 应用程序"部分中的[部署应用程序的最佳做法](../technical-guides/best-practices-for-deploying-an-application.md)<br />-"导出 BizTalk 应用程序"一节[部署应用程序的已知问题](../technical-guides/known-issues-with-deploying-an-application.md)。|  
|绑定文件中的绑定导入到目标应用程序。|-   [如何从绑定文件导入绑定](../technical-guides/how-to-import-bindings-from-a-binding-file.md)<br />-"导入 BizTalk 应用程序"部分中的[部署应用程序的最佳做法](../technical-guides/best-practices-for-deploying-an-application.md)<br />-"导入 BizTalk 应用程序"一节[部署应用程序的已知问题](../technical-guides/known-issues-with-deploying-an-application.md)。|