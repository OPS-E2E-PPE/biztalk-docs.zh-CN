---
title: 如何配置密码同步适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0effdc9b-4aee-4674-90c5-03dfd7cc4cd6
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a82d86947981455cd3ea0d136726a843d385b210
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386987"
---
# <a name="how-to-configure-a-password-sync-adapter"></a>如何配置密码同步适配器
完成创建应用密码同步适配器后，必须加载您登录到系统的适配器。 此外，还必须通知企业单一登录 (ENTSSO) 和配置存储应用程序是密码同步适配器。 必须将注册配置存储区以安全为目的： 您的适配器将会请求更新密码和其他凭据。 因此，ENTSSO 必须知道，一个给定的适配器可以请求此类权限。  
  
### <a name="to-configure-a-password-sync-adapter"></a>若要配置密码同步适配器  
  
1.  使用配置存储区使用 ssops 工具创建您的适配器。  
  
     使用 ssops，XML 配置文件加载到描述为企业单一登录应用程序的配置数据库。  
  
2.  使用配置数据库创建适配器后，可以修改适配器信息`ISSOPSAdmin.SetAdapterProperties`。  
  
     虽然两种方法非常相似，`SetAdapterProperties`配置信息发生更改时向适配器发送消息。  
  
3.  若要删除适配器，请使用 ISSOAdmin.DeleteApplication。  
  
## <a name="see-also"></a>请参阅  
 [同步密码](../core/synchronizing-passwords.md)