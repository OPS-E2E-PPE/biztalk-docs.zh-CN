---
title: 配置 A4SWIFT 用户 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, user accounts
- creating, user accounts
- user accounts, creating
ms.assetid: 45dcbece-ec8d-410a-8320-79bfbc4c779d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79c3b63cd77bb34545f4c4093796310aa7720563
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209373"
---
# <a name="configuring-a4swift-users"></a>配置 A4SWIFT 用户
在安装过程中[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]，A4SWIFT 配置程序创建默认贸易合作伙伴配置文件和协议，并将注册 BizTalk Server。 A4SWIFT 还会创建消息修复和新提交组件使用的文档库。  
  
 在安装期间，A4SWIFT 创建以下文档文件夹：  
  
-   发件箱文档库  
  
-   模板文档库  
  
-   未分析的文档库  
  
-   新 SWIFT MT 消息文档库  
  
-   新建 SWIFT MX 消息文档库  
  
 每个部门创建、 A4SWIFT 管理员必须手动站点将组设置为相应的部门和 A4SWIFT 定义角色。 每个部门/角色具有自动创建配置文件 Web Client(PWC) 的收件箱。  
  
 A4SWIFT 安装配置程序完成后，A4SWIFT 管理员在组织中配置为每个部门的工作流。 消息修复和新提交在配置期间，通过配置文件的 Web 客户端，为每个部门/角色组合将创建相应的收件箱。 例如，在 PWC 配置期间 A4SWIFT 管理员创建名为付款的部门并且然后将的创建者、 Repairers 和审批者角色分配给调用付款的部门。 MRSR 站点上的文档库创建的收件箱名称下表中的示例中所示：  
  
|部门名称|角色名称|收件箱名称|  
|---------------------|---------------|----------------|  
|支付|创建者|Payments_Creator|  
|支付|Repairers|Payments_Repairers|  
|支付|审批者|Payments_Approvers|