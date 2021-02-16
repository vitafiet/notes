# Jenkins does not display HTML artifacts with CSS/formatting.

CSS is stripped out because of the Content Security Policy in Jenkins ([more details.](https://www.jenkins.io/doc/book/system-administration/security/configuring-content-security-policy/))

To relax this content-security-policy, go to:
1. Manage Jenkins
2. Manage Nodes
3. Click settings (gear icon next to the `"master"` node).
4. Click `Script Console` on the left
5. Type the following and click `Run`.
```
System.setProperty("hudson.model.DirectoryBrowserSupport.CSP", "")
```

**Note:** To read the current value of this property, you can use:
```
System.getProperty("hudson.model.DirectoryBrowserSupport.CSP")
```

# Jenkins support for YAML (in Groovy-Scripts for Active Choices parameters)

