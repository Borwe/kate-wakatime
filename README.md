# How to use

1. Get an account at [WakaTime](https://wakatime.com).
2. Get your [API key](https://wakatime.com/settings).
3. Create a file `~/.wakatime.cfg` and make sure it looks similar to this:

   ```ini
   [settings]
   api_key = myapikey-0000-0000-0000-000000000000
   ```

4. Install QJson library.
5. Clone this project and compile:

   ```bash
   git clone git@github.com:Tatsh/kate-wakatime.git
   cd kate-wakatime
   mkdir build
   cd build
   ```

   If on 64-bit:

   ```bash
   cmake ../WakaTime -DCMAKE_INSTALL_PREFIX=/usr
   ```

   If on 32-bit:

   ```bash
   cmake ../WakaTime -DCMAKE_INSTALL_PREFIX=/usr -DLIB_SUFFIX="" -DAutomoc4_DIR=/usr/lib/automoc4
   ```

   ```bash
   make
   ```

6. You can choose to install with `sudo make install` or you can set the `KDEDIRS` environment variable.
7. Once this plugin is installed, open Kate (or any other katepart editor (KWrite, etc)) and go to *Settings*, *Configure <name>...*, then in the dialog choose *Extensions*.
8. Use the checkbox to enable *WakaTime* and click *OK*.
9. Restart Kate to be sure the plugin initialises properly.

Make sure you absolutely have your `~/.wakatime.cfg` file properly set.

# Is this a keylogger?

Short answer is no.

See the [`WakaTimeView::sendAction()`](https://github.com/Tatsh/kate-wakatime/blob/master/WakaTime/wakatimeplugin.cpp#L104) method if you want to be certain.