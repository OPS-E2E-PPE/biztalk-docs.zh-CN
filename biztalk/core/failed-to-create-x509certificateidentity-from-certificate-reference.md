---
title: 未能从证书引用创建 X509CertificateIdentity |Microsoft Docs
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
ms.openlocfilehash: 6cb054a9e062eed58d8fe7469254301f416d7ed0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345948"
---
# <a name="failed-to-create-x509certificateidentity-from-certificate-reference"></a>未能从证书引用创建 X509CertificateIdentity
## <a name="details"></a>详细信息  

|                 |                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                             |
| 产品版本 |                                         [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                         |
|    事件 ID     |                                                                     0                                                                      |
|  事件源   |                                                                     0                                                                      |
|    组件    |                                                                     0                                                                      |
|  符号名称  |                                                                     0                                                                      |
|  消息正文   | 从证书引用创建 X509CertificateIdentity 失败。 (StoreName={0}, StoreLocation={1}, X509FindType={2}, FindValue="{3}") |

## <a name="explanation"></a>解释  
 此错误表示适配器无法创建终结点标识配置中指定的 X509Certificate。  

## <a name="user-action"></a>用户操作  
 使用以下过程来验证证书引用设置。  

#### <a name="to-configure-the-certificate-reference-settings"></a>若要配置证书引用设置  

1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  

3. 找到你的应用程序，然后找到您的传输。  

4. 右键单击传输名称。  

5. 单击 **“属性”**。  

6. 在端口**类型**列表中，选择正确的端口。  

7. 单击**配置**。  

8. 在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**常规**选项卡。  

9. 在中**终结点标识**部分中，单击**编辑。**  

10. 在中**标识编辑器**对话框框中，确保**证书引用**设置是否有效。
