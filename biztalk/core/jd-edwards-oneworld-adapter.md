---
title: 博士 Edwards OneWorld 适配器 |Microsoft 文档
description: 安装、 逐步调试教程，了解体系结构、 使用 SSO 安全、 创建你的应用程序、 导入绑定文件中，并为 J.D.使用 BizTalk 适配器时添加异常处理 BizTalk Server 中的 Edwards OneWorld
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
ms.openlocfilehash: 9bde93503bff679faf2717edefb386aa2f43fc3e
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015926"
---
# <a name="jd-edwards-oneworld-adapter"></a>JD Edwards OneWorld 适配器
通过用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器，可以在 BizTalk Server 中使用 JD Edwards OneWorld 业务功能。 以下部分讨论设置用于 JD Edwards OneWorld 的 BizTalk 适配器，以访问特定于 JD Edwards OneWorld 的信息。  
  
## <a name="get-started"></a>要开始 
[要开始](../core/getting-started-with-biztalk-adapter-for-jd-edwards-oneworld.md)列出要安装适配器，并单步教程的步骤。

## <a name="architecture"></a>体系结构
[体系结构](../core/planning-and-architecture17.md)详细说明了适配器的工作原理，如何实例和函数建立池连接在设计时和运行的时，限制时查询和检索列出，并且使用了此适配器的多订单项。

## <a name="security"></a>安全性
[用于博士 Edwards OneWorld 的 BizTalk Adapter 中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)内 BizTalk Serer 来保护你的应用程序使用此适配器，需使用企业单一登录 (SSO)。

## <a name="create-the-artifacts"></a>创建项目
[创建应用程序项目](../core/developing-applications3.md)演示如何在 BizTalk 管理，和 Visual Studio 中添加项目。 它还演示如何在业务流程中使用消息上下文属性。

## <a name="import-your-app"></a>导入你的应用程序
[为博士 Edwards OneWorld 部署的 BizTalk Adapter](../core/deploying-biztalk-adapter-for-jd-edwards-oneworld.md)讨论如何将应用程序绑定文件导入 BizTalk 管理并超过限制。 

## <a name="exception-handling"></a>异常处理 
[BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling1.md)提供有关更新 jdearglist.txt 文件，并将不同的形状添加到您的业务流程来处理异常的指导。

## <a name="troubleshooting"></a>故障排除
[故障排除](../core/troubleshooting-jd-edwards-oneworld.md)介绍一些常见的错误和情况下，并讨论了 Windows 事件跟踪。

## <a name="data-types"></a>数据类型
[附录： 数据类型](../core/appendix-a-data-types.md)列出此适配器使用的示例数据类型。

## <a name="ui-reference"></a>用户界面参考
[用于 JDE OneWorld 的 BizTalk Adapter 的用户界面参考](../core/ui-reference-for-biztalk-adapter-for-jde-oneworld.md)提供有关显示的对话框和向导使用此适配器的详细信息。 