---
title: JD Edwards OneWorld 适配器 |Microsoft Docs
description: 安装、 单步执行教程，了解体系结构、 使用 SSO 安全性、 创建您的应用程序、 导入绑定文件中，和使用用于 J.D.的 BizTalk 适配器时添加异常处理 在 BizTalk Server 中的 Edwards OneWorld
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5df8cd89-d9df-41ca-9a2c-b9d7fbcd06f2
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ef563da19f04c940aa7f02f700f3b38fa79b1ff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380787"
---
# <a name="jd-edwards-oneworld-adapter"></a>JD Edwards OneWorld Adapter
用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器，可使用 BizTalk Server 中的 JD Edwards OneWorld 业务功能。 以下部分介绍访问特定于 JD Edwards OneWorld 的信息适用于 JD Edwards OneWorld 设置 BizTalk 适配器。  
  
## <a name="get-started"></a>入门 
[开始](../core/getting-started-with-biztalk-adapter-for-jd-edwards-oneworld.md)列出了安装适配器，并单步执行本教程的步骤。

## <a name="architecture"></a>体系结构
[体系结构](../core/planning-and-architecture17.md)详细介绍该适配器的工作原理，如何实例和函数共用在设计时和运行的时，限制时查询和检索列表，并使用此适配器使用 multi-order 项。

## <a name="security"></a>安全性
[用于 JD Edwards OneWorld 的 BizTalk 适配器中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)中 BizTalk 服务器以保护应用程序使用此适配器，需使用企业单一登录 (SSO)。

## <a name="create-the-artifacts"></a>创建的项目
[创建应用程序项目](../core/developing-applications3.md)演示如何在 BizTalk 管理，并在 Visual Studio 中添加项目。 它还演示如何在业务流程中使用消息上下文属性。

## <a name="import-your-app"></a>导入您的应用程序
[部署用于 JD Edwards OneWorld 的 BizTalk 适配器](../core/deploying-biztalk-adapter-for-jd-edwards-oneworld.md)讨论了如何将应用程序的绑定文件导入到 BizTalk 管理并超过限制。 

## <a name="exception-handling"></a>异常处理 
[BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling1.md)指导更新 jdearglist.txt 文件中，并将不同的形状添加到您的业务流程来处理异常。

## <a name="troubleshooting"></a>疑难解答
[故障排除](../core/troubleshooting-jd-edwards-oneworld.md)介绍一些常见的错误和情况下，并讨论了 Windows 的事件跟踪。

## <a name="data-types"></a>数据类型
[附录：数据类型](../core/appendix-a-data-types.md)列出了使用此适配器的示例数据类型。

## <a name="ui-reference"></a>用户界面参考
[用于 JDE OneWorld 的 BizTalk 适配器用户界面参考](../core/ui-reference-for-biztalk-adapter-for-jde-oneworld.md)提供对话框和向导使用此适配器的详细信息。 