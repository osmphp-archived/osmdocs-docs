# Using Custom Web Domains

By default, every book's root URL is `https://osmdocs.com/{user}/{book}/`.

If you have purchased your own domain, show your book on it instead. So that book's root URL becomes `https://yourdomain.com/`.

This user guide is an example of using custom domain for book's root URL. As you can see, its URL is `https://docs.osmdocs.com`.

1. In OsmDocs book settings, enter the name of your domain into the `Web Domain` field and press `Configure DNS` button. Follow the instructions - configure your DNS settings in provider's control panel to resolve your domain to the IP address of OsmDocs server. **Don't save** the book settings!

2. Wait. The changes you made in DNS settings in your provider's control panel will take some time to take effect up to one day. Use `ping {your_domain}` command in the shell to check whether the changes have been applied - it should show the IP address of the OsmDocs server.

3. Enter the name of your domain into the `Web Domain` field in the OsmDocs book settings and this time save the changes. 

