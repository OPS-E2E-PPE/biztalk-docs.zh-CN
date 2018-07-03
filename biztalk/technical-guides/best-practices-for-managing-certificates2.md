---
title: 用于管理 Certificates2 最佳做法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71fa00cc-2e0c-46b3-ae62-f130a5b5f4f5
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e2b79e2a0d7e4758ac87503f4bfac122c9ee215
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994782"
---
# <a name="best-practices-for-managing-certificates"></a>管理证书的最佳实践
本部分提供有关在 Microsoft BizTalk Server 环境中管理证书的最佳实践。  
  
## <a name="assess-and-plan-your-use-of-certificates"></a>评估和规划证书的使用  
 **进行威胁模型分析您的环境**  
  
- 对您的环境进行威胁模型分析可以确定签名证书和加密证书是否有助于缓解安全威胁。  
  
  **创建与合作伙伴的公钥证书计划**  
  
- 创建发送到的公钥证书和从合作伙伴接收的公钥证书的计划。 如果您不准备使用签名证书进行参与方解析，则公共证书可以附加到消息上，在此情况下，您无需事先在系统中复制证书。  
  
  **指导原则与合作伙伴建立提交公钥的**  
  
- 在与合作伙伴达成的服务级别协议 (SLA) 中，建立提交公钥的准则以及在他们的证书即将过期或要吊销证书时通知您。  
  
## <a name="install-certificates"></a>安装证书  
 **在设置的时间间隔下载证书吊销列表**  
  
- 以固定的时间间隔从证书颁发机构 (CA) 下载证书吊销列表 (CRL)。 建议每周进行一次。 对于 BizTalk Server 所加入的域，如果有 CA 存在，则将自动下载 CRL。  
  
  **验证签名证书**  
  
- 确保根据证书吊销列表来验证签名证书。 有关如何验证签名证书的详细信息，请参阅[如何配置 MIME/SMIME 解码器管道组件](http://go.microsoft.com/fwlink/?LinkId=155145)(<http://go.microsoft.com/fwlink/?LinkId=155145>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
  **管理证书与合作伙伴**  
  
- 将证书管理作为您的合作伙伴管理实践的一部分。 在 BizTalk Server 环境中添加或删除参与方时，建议您添加或删除与该合作伙伴相关联的各个证书。  
  
  **删除主机实例前删除证书**  
  
- 在从 BizTalk Server 中删除主机实例前，先删除运行该主机实例的帐户的个人存储中的证书。  
  
## <a name="configure-biztalk-server-to-use-certificates-for-mimesmime"></a>配置 BizTalk Server 以便使用 MIME/SMIME 证书  
 **避免拒绝服务攻击的数字签名**  
  
- 确定你想要在 BizTalk Server 无法验证数字签名时使用消息执行操作。 设置接收端口上的身份验证属性有助于防止拒绝服务攻击。  
  
  > [!NOTE]
  >  身份验证-删除消息和身份验证-保留消息的接收端口上的标志需要正确配置参与方解析管道组件和 BizTalk Server 中，定义参与方。 有关详细信息，请参阅[参与方解析管道组件](http://go.microsoft.com/fwlink/?LinkId=155146)(<http://go.microsoft.com/fwlink/?LinkId=155146>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
  **创建单独的加密和未加密消息接收位置**  
  
- 如果计划从某些合作伙伴接收 MIME 加密的消息而从其他合作伙伴接收未加密的消息，请在不同主机上为加密消息和未加密消息创建单独的接收位置。 要得到仅 MIME 加密的消息，请配置允许非 MIME 消息选项在解码 MIME/SMIME 管道组件中为 no。  
  
## <a name="configure-a-biztalk-adapter-to-use-certificates"></a>配置为使用证书的 BizTalk 适配器  
 **测试与目标网站的连接**  
  
- 如果在使用 SSL，确保你可以连接到目标 Web 站点使用 Microsoft Internet Explorer® 然后再尝试连接到目标网站，使用 HTTP 或 SOAP 传输。 验证连接到目标网站时无对话框显示在 Internet Explorer 中。 BizTalk Server 已连接的任何机制与连接到目标网站时可能会显示任何对话框。 Internet Explorer 可能会显示一个对话框，如果目标网站名称不匹配的 SSL 证书中的 Web 站点为指定的名称或根证书颁发机构的 SSL 证书不在相应的受信任的根证书颁发机构存储区。  
  
  **使用 SSL 诊断工具可以分析 SSL 连接问题**  
  
- SSL 诊断工具是 IIS 诊断工具包的可选组件。 您可以下载 IIS 诊断工具包从[Internet 信息服务诊断工具](http://go.microsoft.com/fwlink/?LinkID=64426)页 (http://go.microsoft.com/fwlink/?LinkID=64426)。  
  
## <a name="exporting-a-certificate-from-one-biztalk-group-to-another"></a>将证书从一个 BizTalk 组导出到另一个  
 **请确保导入的证书，用于其预期目的**  
  
-   如果证书导入组后，导入的证书必须符合其预期用途的使用情况属性。 若要检查的使用情况属性，请双击中的证书**证书管理控制台**接口，然后依次**详细信息**选项卡**证书**对话框。 然后单击**所有**选项**显示**下拉列表，然后单击此项可选择**密钥用法**和/或**增强型密钥用法**字段若要验证的预期的用途。 如果 BizTalk Server 尝试使用超出预期用途的证书将发生运行时错误。