---
title: 在一个 SAP 用于 BizTalk 中的 SAP 适配器创建 RFC 概述 |Microsoft 文档
description: 创建 RFC，RFC 目标和发送 RFC 从 SAP 系统-BizTalk 适配器包 (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35937183-fc1e-49cd-8a75-8f62effe0013
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 802a2e33b8bc902dc784276ce7c1d9c3f37f3b12
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216517"
---
# <a name="create-and-send-an-rfc-in-sap"></a>创建和 SAP 中发送 RFC
列出在该 SAP 系统创建 RFC 上完成的高级任务。 每个任务可能涉及到非常详细的过程。 因此，我们建议联系您的 SAP 管理员来完成这些任务，或指 SAP 指南。  
  
## <a name="create-an-rfc"></a>创建 RFC  
  
1.  启动 SAP GUI。  
  
2.  转到事务 SE37 （函数生成器） 中，输入 RFC 名称，然后单击**创建**。  
  
3.  输入现有函数组在其下将创建 RFC，RFC，有关的简短说明，然后单击**保存**。  
  
4.  在**属性**选项卡上，选择**Remote-Enabled 模块**单选按钮。  
  
5.  在**导入**选项卡上，输入导入参数。 这些参数用于将外部数据传递给函数模块。  
  
6.  在**导出**选项卡上，输入导出参数。  
  
7.  在**Changing**选项卡上，输入不断变化的参数。  
  
8.  在**表**选项卡上，输入表名称。  
  
9. 在**异常**选项卡上，输入来处理错误的异常。  
  
10. 在**源代码**选项卡上，输入 RFC 源代码 （逻辑）。  
  
11. 单击**激活**工具栏激活函数模块上的图标。  

## <a name="create-an-rfc-destination"></a>创建一个 RFC 目标  
  
1.  启动 SAP GUI。  
  
2.  转到事务 SM59 （显示和维护 RFC 目标）。  
  
3.  从菜单栏中，单击**创建**。  
  
4.  输入 RFC 目标、 连接类型、 说明，，然后按 enter 键。  
  
5.  选择**注册服务器程序**单选按钮输入程序 ID、 网关主机和网关服务。  
  
6.  保存 RFC 目标。  

## <a name="send-an-rfc-from-an-sap-system"></a>从 SAP 系统发送 RFC  
  
1.  启动 SAP GUI。  
  
2.  创建使用 BD54 事务的逻辑系统。  
  
3.  创建一个 RFC 目标中使用 SM59 事务的 TCP/IP 连接。  
  
4.  创建使用 WE21 事务的端口，并将其附加到的最后一步中创建的 RFC 目标。  
  
5.  通过使用 SE37 触发 RFC。 此 RFC 必须包含逻辑以便进行 RFC 调用外部应用程序，然后从该应用程序收到的响应。  
  
## <a name="see-also"></a>另请参阅  
 [对于特定 SAP 适配器方案中使用 SAP GUI 执行任务](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)