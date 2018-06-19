---
title: 未能从证书引用创建 X509CertificateIdentity |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3acee8e-c035-4e58-8bfc-397885b4d185
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c6bb03698010d667b27334f17fa7270de845c68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246061"
---
# <a name="failed-to-create-x509certificateidentity-from-certificate-reference"></a>未能从证书引用创建 X509CertificateIdentity
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|从证书引用创建 X509CertificateIdentity 时失败。 (StoreName = {0}，StoreLocation = \ {1 \}，X509FindType = \ {2 \}，FindValue ="\ {3\}")|  
  
## <a name="explanation"></a>解释  
 此错误表示适配器创建在终结点标识配置中指定的 X509Certificate 时失败。  
  
## <a name="user-action"></a>用户操作  
 使用以下过程验证证书引用设置。  
  
#### <a name="to-configure-the-certificate-reference-settings"></a>配置证书引用设置的步骤  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  找到应用程序，然后找到您的传输。  
  
4.  右键单击传输名称。  
  
5.  单击 **“属性”**。  
  
6.  在端口**类型**列表中，选择正确的端口。  
  
7.  单击**配置**。  
  
8.  在**WCF [***传输类型***] 传输属性**对话框中，单击**常规**选项卡。  
  
9. 在**终结点标识**部分中，单击**编辑。**  
  
10. 在**标识编辑器**对话框框中，确保**证书引用**设置都是有效。