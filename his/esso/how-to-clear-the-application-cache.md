---
title: 如何清除应用程序缓存 |Microsoft 文档
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a897791-d32f-46a4-8c5d-2b2161e92bd9
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 24954e8314bc94d4570eb57acbf1d4b03bebb65b
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-clear-the-application-cache"></a>如何清除应用程序缓存
使用 Mmc 管理单元或**purgecache**命令，以删除凭据缓存 （所有的信息与关联应用程序关联） 的内容的所有单一登录 (SSO) 服务器上指定的应用程序。  
  
### <a name="to-clear-the-cache-using-the-mmc-snap-in"></a>若要清除缓存使用 Mmc 管理单元  
  
1.  单击**启动**，指向**程序**，单击**Microsoft Enterprise 上单一登录**，然后单击**SSO 管理**。  
  
2.  在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。  
  
3.  单击 **Affiliate 应用程序**。  
  
4.  在结果窗格中，右键单击关联应用程序，然后单击 **清除**。  
  
### <a name="to-clear-the-cache-using-the-command-line"></a>若要清除缓存使用命令行  
  
1.  单击 **启动**, ，单击 **运行**, ，类型 `cmd`, ，然后按 ENTER。  
  
2.  在命令提示符处，转到企业单一登录安装目录。  
  
     默认安装目录是\<*驱动器*>: \program Files\Enterprise 单一登录。  
  
3.  类型`ssomanage –purgecache <application name>`，其中\<*应用程序名称*> 是你想要清除的缓存的关联应用程序的名称。  
  
## <a name="see-also"></a>另请参阅  
 [SSO 关联应用程序](../esso/sso-affiliate-applications.md)   
 [管理关联应用程序](../esso/managing-affiliate-applications.md)