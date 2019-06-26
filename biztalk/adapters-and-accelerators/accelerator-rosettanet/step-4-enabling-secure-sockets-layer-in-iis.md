---
title: 步骤 4：启用安全套接字在 IIS 中的层 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Secure Socket Layers
- IIS
- double action tutorial, enabling SSL in IIS
- SSL
ms.assetid: 96109294-595a-46ac-974e-33123df79ed5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d12914621e8b9200f3f86e486caee964473f01d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280908"
---
# <a name="step-4-enabling-secure-sockets-layer-in-iis"></a>步骤 4：启用安全套接字在 IIS 中的层
安全套接字层 (SSL) 是旨在保护客户端和服务器之间的通信通道的安全协议。 通过启用 SSL 在 Microsoft® Internet 信息服务 (IIS) 7.5/7.0，Contoso 和 Fabrikam 组织在通信中对所有数据传输使用身份验证和加密。 在此步骤中，您将了解如何启用 SSL IIS 7.5/7.0。  
  
> [!NOTE]
>  必须在 Contoso 和 Fabrikam 计算机上执行此步骤。  
  
### <a name="to-prepare-a-new-server-certificate"></a>若要准备新的服务器证书  
  
1. 单击**启动**，依次指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。  
  
2. 在 Internet Information Services 的左窗格中，展开 **\<** <em>computer_name</em> **\>** (*本地计算机*)，展开**网站**，右键单击**Default Web Site**，然后单击**属性**。  
  
3. 在默认网站对话框中，在**目录安全性**选项卡上，单击**服务器证书**以启动**IIS 证书向导**。  
  
4. 上**欢迎使用 Web 服务器证书向导**页上，单击**下一步**。  
  
5. 上**服务器证书**页上，选择**创建新证书**，然后单击**下一步**。  
  
6. 上**延迟或立即请求**页上，单击**下一步**。  
  
7. 上**名称和安全设置**页上，单击**下一步**，保留默认值。  
  
8. 上**组织信息**页上，在**组织**框中，键入**Contoso**如果 Contoso 计算机上的或**Fabrikam**如果已打开Fabrikam 计算机，请在**组织单位**框中，键入**测试**，然后单击**下一步**。  
  
9. 上**站点的公用名称**页上，在**公用名**框中，键入您的计算机的名称，然后单击**下一步**。  
  
10. 上**地理信息**页上，在**省/市/自治区**框中，键入您的州/省，在**市/县**中，键入您的市/县，，然后单击**下一步**。  
  
11. 上**证书请求文件名**页上，在**文件名**框中，保留默认值**C:\certreq.txt**，然后单击**下一步**。  
  
12. 上**请求文件摘要**页上，单击**下一步**。  
  
13. 上**完成 Web 服务器证书向导**页上，单击**完成**以关闭**IIS 证书向导**。  
  
### <a name="to-generate-a-new-server-certificate"></a>若要生成新的服务器证书  
  
1.  在 Internet Explorer 中，找到并打开 http://\<*contoso 计算机*\>/CertSrv。  
  
    > [!NOTE]
    >  在步骤 1 中，打开 http://\<*contoso 计算机*\>/CertSrv Contoso 或 Fabrikam 计算机上的。  
  
2.  上**Microsoft 证书服务向导欢迎**页上，单击**申请一个证书。**  
  
3.  上**申请一个证书**页上，单击**高级的证书申请**。  
  
4.  上**高级证书申请**页上，单击**使用 base-64 编码的 CMC 或 PKCS #10 文件，提交证书申请或使用 base 64 编码的 PKCS #7 文件提交续订申请**。  
  
5.  上**提交证书申请或续订申请**页上，单击**浏览文件插入**。  
  
    > [!NOTE]
    >  如果单击链接时接收到安全性错误，在记事本或其他文本编辑器中打开文件 C:\certreq.txt，复制该文件的内容并将该信息粘贴**保存的申请**框中，然后依次**提交**。 然后，可以转到步骤 10。  
  
6.  单击**浏览**以打开**选择文件**对话框。  
  
7.  在中**选择文件**对话框框中，找到 *\<驱动器\>* : \ 文件夹中，选择 certreq.txt 文件，然后单击**打开**。  
  
8.  上**提交证书申请或续订申请**页上，单击**读取**。  
  
9. 上**提交证书申请或续订申请**页上，单击**提交**以生成新证书。  
  
10. 上**证书颁发**页上，单击**下载的证书**。  
  
11. 在中**文件下载**对话框中，单击**保存**。  
  
12. 在中**另存为**对话框中的，保存到证书\<驱动器\>: \Certs\SSLCert.cer，，然后单击**保存**。  
  
13. 单击**关闭**以关闭**下载完整**对话框。  
  
### <a name="to-prepare-a-new-server-certificate-for-iis"></a>若要为 IIS 准备新的服务器证书  
  
1.  单击**启动**，依次指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。  
  
2.  在 Internet Information Services 的左窗格中，单击 < 计算机名 > （本地计算机），双击**服务器证书**右窗格中。 选择**创建证书申请**从操作窗格。  
  
3.  可分辨名称属性对话框中键入的公用名中的计算机的名称： 文本框中，组织中： 框中，键入**Contoso**如果在 Contoso 计算机上的或**Fabrikam**如果已打开 Fabrikam计算机上的组织单位： 框中，键入测试，请在市/县框中，州/省框中键入您的市/县中,，键入您的州/省，国家/地区下拉列表中选择您所在国家/地区，然后单击**下一步**.  
  
4.  在加密服务提供程序属性对话框中，单击**下一步**。  
  
5.  在文件名对话框中，在文本框中，指定 C:\certreq.txt 单击**完成**。  
  
### <a name="to-generate-a-new-server-certificate-for-iis"></a>若要为 IIS 生成新的服务器证书  
  
1.  在 Internet Explorer 中，找到并打开 http://<contoso_machine>/CertSrv。  
  
    > [!NOTE]
    >  在步骤 1 中，打开 http://<contoso_machine>/CertSrv Contoso 或 Fabrikam 计算机上。  
  
2.  在 Microsoft 证书服务向导欢迎页上，单击**申请一个证书**。  
  
3.  在请求证书页上，单击**高级证书申请**。  
  
4.  在高级证书申请页上，单击**提交证书申请**通过使用 base-64 编码的 CMC 或 PKCS #10 文件，或使用 base 64 编码的 PKCS #7 文件提交续订申请。  
  
5.  在记事本或其他文本编辑器中打开文件 C:\certreq.txt，复制该文件的内容并将该信息粘贴**保存的申请**框上提交证书申请或续订申请的页上，然后依次**提交**。  
  
6.  在证书已颁发页上，单击**下载证书**。  
  
7.  在文件下载对话框中，单击**保存**。  
  
8.  在另存为对话框中，将保存到证书\<驱动器\>: \Certs\SSLCert.cer，并单击**保存**。  
  
### <a name="to-import-the-server-certificate-into-iis"></a>服务器证书导入到 IIS  
  
1.  单击**启动**，依次指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。  
  
2.  在 Internet Information Services 的左窗格中，单击 **（本地计算机）** ，双击**服务器证书**右窗格中。 选择**完成证书申请**从操作窗格。  
  
3.  在指定的证书颁发机构响应对话框框中键入 **\<驱动器\>: \Certs\SSLCert.cer**中**包含证书颁发机构的响应文件的名称**文本框。 中的友好名称文本框中键入**ContosoSSLCert**。  
  
### <a name="to-enable-ssl-bindings-for-iis"></a>若要启用 IIS 的 SSL 绑定  
  
1.  单击**启动**，依次指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。  
  
2.  在 Internet Information Services 的左窗格中，展开 **（本地计算机）** ，展开**站点**，右键单击**Default Web Site**，然后单击**编辑绑定**。  
  
3.  在站点绑定对话框中单击**添加**。 在添加网站绑定对话框中选择**https**从类型下拉列表中，选择**ContosoSSLCert** SSL 证书下拉列表中，单击**确定**，单击**关闭**.  
  
### <a name="to-import-the-server-certificate-into-iis"></a>服务器证书导入到 IIS  
  
1. 单击**启动**，依次指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。  
  
2. 在 Internet Information Services 的左窗格中，展开 **\<** <em>computer_name</em> \> (*本地计算机*)，展开**Web站点**，右键单击**Default Web Site**，然后单击**属性**。  
  
3. 在默认网站属性对话框中，在**目录安全性**选项卡上，单击**服务器证书**以启动**IIS 证书向导**。  
  
4. 上**欢迎使用 Web 服务器证书向导**页上，单击**下一步**。  
  
5. 上**挂起的证书申请**页上，选择**处理挂起的请求和安装证书**，然后单击**下一步**。  
  
6. 上**处理挂起的申请**页上，在**路径和文件名**框中，键入 **\<驱动器\>: \Certs\SSLCert.cer** （或浏览到该文件）然后单击**下一步**。  
  
7. 上**SSL 端口页**，单击**下一步**。  
  
8. 上**证书摘要**页上，单击**下一步**。  
  
9. 上**完成 Web 服务器证书向导**页上，单击**完成**。  
  
## <a name="see-also"></a>请参阅  
 [创建和配置 Contoso 解决方案](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-contoso-solution.md)