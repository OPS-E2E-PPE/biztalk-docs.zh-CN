---
title: 概述了如何创建要与 BizTalk 中的 SAP 适配器使用 sap RFC |Microsoft Docs
description: 创建 RFC 和 RFC 目标和发送从 SAP 系统的 BizTalk 适配器包 (BAP) 的 RFC
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
ms.openlocfilehash: 4c05fb0b0c987c4f04115f6872056beeaf260355
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373532"
---
# <a name="create-and-send-an-rfc-in-sap"></a>创建并在 SAP 发送 RFC
列出要完成 SAP 系统，为创建 RFC 上的高级任务。 每个任务可能涉及非常详细的过程。 因此，我们建议联系你的 SAP 管理员要完成这些任务，或请参阅 SAP 指南。  
  
## <a name="create-an-rfc"></a>创建 RFC  
  
1.  启动将 SAP GUI。  
  
2.  转到事务 SE37 （函数生成器） 中，输入 RFC 名称，然后单击**创建**。  
  
3.  输入现有函数组将下创建 RFC，RFC 的简短说明，然后单击**保存**。  
  
4.  在中**特性**选项卡上，选择**Remote-Enabled 模块**单选按钮。  
  
5.  在中**导入**选项卡上，输入导入参数。 这些参数用于将外部数据传递到函数模块。  
  
6.  在中**导出**选项卡上，输入导出参数。  
  
7.  在中**Changing**选项卡上，输入更改的参数。  
  
8.  在中**表**选项卡上，输入表名称。  
  
9. 在中**异常**选项卡上，输入来处理错误的异常。  
  
10. 在中**源代码**选项卡上，输入在 RFC 的源代码 （逻辑）。  
  
11. 单击**激活**激活函数模块在工具栏上的图标。  

## <a name="create-an-rfc-destination"></a>创建一个 RFC 目标  
  
1.  启动将 SAP GUI。  
  
2.  转到事务 SM59 （显示和维护 RFC 目标）。  
  
3.  从菜单栏中，单击**创建**。  
  
4.  输入的 RFC 目标、 连接类型、 说明，然后按 Enter。  
  
5.  选择**注册服务器程序**单选按钮输入程序 ID、 网关主机和网关服务。  
  
6.  保存的 RFC 目标。  

## <a name="send-an-rfc-from-an-sap-system"></a>从 SAP 系统发送 RFC  
  
1.  启动将 SAP GUI。  
  
2.  创建使用 BD54 事务的逻辑系统。  
  
3.  在使用 SM59 事务的 TCP/IP 连接中创建的 RFC 目标。  
  
4.  创建使用 WE21 事务的端口，并将其附加到的最后一步中创建的 RFC 目标。  
  
5.  通过使用 SE37 触发 RFC。 此 RFC 必须包含逻辑，以便调用外部应用程序，并从该应用程序接收响应的 RFC。  
  
## <a name="see-also"></a>请参阅  
 [特定的 SAP 适配器方案中使用 SAP GUI 执行任务](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)