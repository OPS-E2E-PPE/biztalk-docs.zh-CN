---
title: 单一登录： 事件 10765 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e28fe42e-aa2b-4be4-b757-bc9c5c37526b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd49ead3fc30d3b98ea804a98a5882696ea749d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975102"
---
# <a name="single-sign-on-event-10765"></a>单一登录： 事件 10765
## <a name="details"></a>详细信息  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           10765                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                            N/A                             |
|  符号名称  |                  ENTSSO_E_NO_CREDENTIALS                   |
|  消息正文   |       尚未为此映射设置凭据。        |
  
## <a name="explanation"></a>解释  
 您请求了一个映射的 GetCredentials，但指定的映射没有凭据。  
  
## <a name="user-action"></a>用户操作  
 使用命令行或 MMC 管理单元为映射设置凭据。