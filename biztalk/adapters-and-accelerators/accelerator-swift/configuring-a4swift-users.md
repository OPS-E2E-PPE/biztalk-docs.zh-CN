---
title: 配置 A4SWIFT 用户 |Microsoft Docs
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
ms.openlocfilehash: e928e05d1f0890d534fe768f843e5fe945706856
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65527581"
---
# <a name="configuring-a4swift-users"></a>配置 A4SWIFT 用户
安装过程中的[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]，A4SWIFT 配置程序创建默认贸易合作伙伴配置文件和协议，并将注册 BizTalk Server。 A4SWIFT 还会创建消息修复和新提交组件使用的文档库。  
  
 A4SWIFT 安装过程中创建以下文档文件夹：  
  
- 发件箱文档库  
  
- 模板文档库  
  
- 未分析的文档库  
  
- 新 SWIFT MT 消息文档库  
  
- 新 SWIFT MX 消息文档库  
  
  每个部门创建，A4SWIFT 管理员必须手动设置了相应的部门的站点组和 A4SWIFT 定义的角色。 每个部门/角色具有自动创建的配置文件 Web Client(PWC) 收件箱。  
  
  A4SWIFT 安装配置程序完成后，A4SWIFT 管理员在组织中配置的每个部门的工作流。 消息修复和新提交在配置期间，通过配置文件 Web 客户端，为每个部门/角色组合创建相应的收件箱。 例如，在 PWC 配置期间 A4SWIFT 管理员创建名为付款的部门，然后将的创建者、 Repairers 和审批者角色分配到名为付款的部门。 MRSR 站点上的文档库创建收件箱名称在下表中的示例中所示：  
  
|部门名称|角色名称|收件箱名称|  
|---------------------|---------------|----------------|  
|付款|创建者|Payments_Creator|  
|付款|Repairers|Payments_Repairers|  
|付款|审批者|Payments_Approvers|