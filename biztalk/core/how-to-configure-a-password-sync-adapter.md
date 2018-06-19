---
title: 如何配置密码同步适配器 |Microsoft 文档
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
ms.openlocfilehash: 3f0be0146e905ef291942bd30adc111eff89e989
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247349"
---
# <a name="how-to-configure-a-password-sync-adapter"></a>如何配置密码同步适配器
创建完密码同步适配器之后，必须将该适配器加载到系统中。 此外，还必须通知企业单一登录 (ENTSSO) 和配置存储，您的应用程序是一个密码同步适配器。 必须将注册配置存储区出于安全目的： 你的适配器将请求更新密码和其他凭据。 因此，ENTSSO 必须知道允许给定的适配器请求此类权限。  
  
### <a name="to-configure-a-password-sync-adapter"></a>配置密码同步适配器  
  
1.  使用 ssops 工具创建具有配置存储的适配器。  
  
     使用 ssops 将 XML 配置文件加载到配置数据库中，以便向企业单一登录描述您的应用程序。  
  
2.  与配置数据库创建适配器之后，你可以修改的适配器信息`ISSOPSAdmin.SetAdapterProperties`。  
  
     尽管两种方法非常相似，`SetAdapterProperties`配置信息更改时，将消息发送到适配器。  
  
3.  若要删除适配器，请使用 ISSOAdmin.DeleteApplication。  
  
## <a name="see-also"></a>另请参阅  
 [同步密码](../core/synchronizing-passwords.md)