---
id: application-yii-2
title: Yii 2
sidebar_label: Yii 2
---

import useBaseUrl from '@docusaurus/useBaseUrl';

On this page, we explain step by step how to setup **Yii 2** with **CloudPanel**.

## Installation

In the following example we will setup **Yii 2** under the domain ***www.domain.com***.

### Preparation

Before we can start with the installation of **Yii 2**, we need to create an [SSH User](users#adding-a-user), a [Database](databases#adding-a-database) <br />
and a [Domain](domains#adding-a-domain).

When you [Add the Domain](domains#adding-a-domain), make sure to select the **Yii 2 Vhost Template** and the right **PHP Version**.

<img class="border" src={useBaseUrl('img/v1/applications/yii-2/new_domain.png')} /> <br /><br />

:::warning Document Root
Make sure to point the **Document Root** to the **web** directory.
:::

### Installation

To install **Yii 2** do the following steps:

1. [Login via SSH](users#ssh-login) to the server e.g. with **john-ssh** and go **htdocs** directory:

```
cd /home/cloudpanel/htdocs/
```

2. Delete the project directory which has been created by **CloudPanel**:

```
rm -rf /home/cloudpanel/htdocs/www.domain.com
```

3. Install via **composer**:

```
php7.4 /usr/local/bin/composer create-project --prefer-dist yiisoft/yii2-app-basic www.domain.com
```

4. Reset permissions.

```
cd /home/cloudpanel/htdocs/
clpctl system:permissions:reset www.domain.com 775
```

5. Done! You can now open your domain in your browser to see the welcome page.

<img class="border" src={useBaseUrl('img/v1/applications/yii-2/welcome.png')} /> 

