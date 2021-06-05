## 4. INTERACTIVE Commands

Listed  below  is  a brief index of commands within categories.  Some commands appear more than once -- their meaning or scope may vary depending on the context in which they are issued.

         4a. Global-Commands
               <Ent/Sp> ?, =, 0,
               A, B, d, E, e, g, h, H, I, k, q, r, s, W, X, Y, Z
         4b. Summary-Area-Commands
               C, l, t, m, 1, 2, 3
         4c. Task-Area-Commands
               Appearance:  b, J, j, x, y, z
               Content:     c, f, F, o, O, S, u, U, V, v
               Size:        #, i, n
               Sorting:     <, >, f, F, R
         4d. Color-Mapping
               <Ret>, a, B, b, H, M, q, S, T, w, z, 0 - 7
         5b. Commands-for-Windows
               -, _, =, +, A, a, g, G, w
         5c. Scrolling-a-Window
               C, Up, Dn, Left, Right, PgUp, PgDn, Home, End
         5d. Searching-in-a-Window
               L, &

### 4a. GLOBAL Commands

The global interactive commands are always available in both full-screen mode and  alternate-display mode.  However, some of these interactive commands are not available when running in Secure mode.

If  you  wish  to  know in advance whether or not your top has been secured, simply ask for help and view the system summary on the second line.

         <Enter> or <Space>  :Refresh-Display
              These commands awaken top and following receipt of any input the entire display will  be  re‐
              painted.  They also force an update of any hotplugged cpu or physical memory changes.

              Use either of these keys if you have a large delay interval and wish to see current status,

          ? | h  :Help
              There  are two help levels available.  The first will provide a reminder of all the basic in‐
              teractive commands.  If top is secured, that screen will be abbreviated.

              Typing `h' or `?' on that help screen will take you to help for  those  interactive  commands
              applicable to alternate-display mode.

          =  :Exit-Task-Limits
              Removes  restrictions  on  which  tasks  are  shown.  This command will reverse any `i' (idle
              tasks), `n' (max tasks) and `v' (hide children) commands that might be active.  It also  pro‐
              vides for an exit from PID monitoring, User filtering, Other filtering and Locate processing.

              Additionally, if the window has been scrolled it will be reset with this command.

          0  :Zero-Suppress toggle
              This  command  determines  whether  zeros are shown or suppressed for many of the fields in a
              task window.  Fields like UID, GID, NI, PR or P are not affected by this toggle.

          A  :Alternate-Display-Mode toggle
              This command will switch between full-screen mode and alternate-display mode.  See  topic  5.
              ALTERNATE-DISPLAY  Provisions and the `g' interactive command for insight into `current' win‐
              dows and field groups.

          B  :Bold-Disable/Enable toggle
              This command will influence use of the bold terminfo capability and alters both  the  summary
              area  and  task  area  for the `current' window.  While it is intended primarily for use with
              dumb terminals, it can be applied anytime.

              Note: When this toggle is On and top is operating in monochrome mode, the entire display will
              appear  as normal text.  Thus, unless the `x' and/or `y' toggles are using reverse for empha‐
              sis, there will be no visual confirmation that they are even on.

       *  d | s  :Change-Delay-Time-interval
              You will be prompted to enter the delay time, in seconds, between display updates.

              Fractional seconds are honored, but a negative number is  not  allowed.   Entering  0  causes
              (nearly)  continuous updates, with an unsatisfactory display as the system and tty driver try
              to keep up with top's demands.  The delay value is inversely proportional to system  loading,
              so set it with care.

              If at any time you wish to know the current delay time, simply ask for help and view the sys‐
              tem summary on the second line.

          E  :Extend-Memory-Scale in Summary Area
              With this command you can cycle through the  available  summary  area  memory  scaling  which
              ranges    from    KiB    (kibibytes    or    1,024   bytes)   through   EiB   (exbibytes   or
              1,152,921,504,606,846,976 bytes).

              If you see a `+' between a displayed number and the following label, it means  that  top  was
              forced  to truncate some portion of that number.  By raising the scaling factor, such trunca‐
              tion can be avoided.

          e  :Extend-Memory-Scale in Task Windows
              With this command you can cycle through the available task window memory scaling which ranges
              from KiB (kibibytes or 1,024 bytes) through PiB (pebibytes or 1,125,899,906,842,624 bytes).

              While top will try to honor the selected target range, additional scaling might still be nec‐
              essary in order to accommodate current values.  If you wish to see a more homogeneous  result
              in  the memory columns, raising the scaling range will usually accomplish that goal.  Raising
              it too high, however, is likely to produce an all zero result which cannot be suppressed with
              the `0' interactive command.

          g  :Choose-Another-Window/Field-Group
              You  will  be  prompted  to  enter a number between 1 and 4 designating the field group which
              should be made the `current' window.  You will soon grow comfortable with  these  4  windows,
              especially after experimenting with alternate-display mode.

          H  :Threads-mode toggle
              When this toggle is On, individual threads will be displayed for all processes in all visible
              task windows.  Otherwise, top displays a summation of all threads in each process.

          I  :Irix/Solaris-Mode toggle
              When operating in Solaris mode (`I' toggled Off), a task's cpu usage will be divided  by  the
              total  number of CPUs.  After issuing this command, you'll be told the new state of this tog‐
              gle.

       *  k  :Kill-a-task
              You will be prompted for a PID and then the signal to send.

              Entering no PID or a negative number will be interpreted as the default shown in  the  prompt
              (the first task displayed).  A PID value of zero means the top program itself.

              The  default  signal, as reflected in the prompt, is SIGTERM.  However, you can send any sig‐
              nal, via number or name.

              If you wish to abort the kill process, do one of the following depending on your progress:
                  1) at the pid prompt, type an invalid number
                  2) at the signal prompt, type 0 (or any invalid signal)
                  3) at any prompt, type <Esc>

          q  :Quit

       *  r  :Renice-a-Task
              You will be prompted for a PID and then the value to nice it to.

              Entering no PID or a negative number will be interpreted as the default shown in  the  prompt
              (the first task displayed).  A PID value of zero means the top program itself.

              A  positive  nice  value  will cause a process to lose priority.  Conversely, a negative nice
              value will cause a process to be viewed more favorably by the kernel.  As a general rule, or‐
              dinary users can only increase the nice value and are prevented from lowering it.

              If you wish to abort the renice process, do one of the following depending on your progress:
                  1) at the pid prompt, type an invalid number
                  2) at the nice prompt, type <Enter> with no input
                  3) at any prompt, type <Esc>

          W  :Write-the-Configuration-File
              This  will save all of your options and toggles plus the current display mode and delay time.
              By issuing this command just before quitting top, you will be able restart later  in  exactly
              that same state.

          X  :Extra-Fixed-Width
              Some  fields are fixed width and not scalable.  As such, they are subject to truncation which
              would be indicated by a `+' in the last position.

              This interactive command can be used to alter the widths of the following fields:

                  field  default    field  default    field  default
                  GID       5       GROUP     8       WCHAN    10
                  RUID      5       LXC       8       nsIPC    10
                  SUID      5       RUSER     8       nsMNT    10
                  UID       5       SUSER     8       nsNET    10
                                    TTY       8       nsPID    10
                                    USER      8       nsUSER   10
                                                      nsUTS    10

              You will be prompted for the amount to be added to the default widths shown above.   Entering
              zero forces a return to those defaults.

              If you enter a negative number, top will automatically increase the column size as needed un‐
              til there is no more truncated data.  You can accelerate this process by reducing  the  delay
              interval or holding down the <Space> bar.

              Note:  Whether  explicitly  or automatically increased, the widths for these fields are never
              decreased by top.  To narrow them you must specify a smaller number or restore the defaults.

          Y  :Inspect-Other-Output
              After issuing the `Y' interactive command, you will be prompted for a target PID.   Typing  a
              value or accepting the default results in a separate screen.  That screen can be used to view
              a variety of files or piped command output while the normal top iterative display is paused.

              Note: This interactive command is only fully realized when supporting entries have been manu‐
              ally  added to the end of the top configuration file.  For details on creating those entries,
              see topic 6b. ADDING INSPECT Entries.

              Most of the keys used to navigate the Inspect feature are reflected in its  header  prologue.
              There  are,  however,  additional  keys available once you have selected a particular file or
              command.  They are familiar to anyone who has used the pager `less' and are  summarized  here
              for future reference.

                  key      function
                  =        alternate status-line, file or pipeline
                  /        find, equivalent to `L' locate
                  n        find next, equivalent to `&' locate next
                  <Space>  scroll down, equivalent to <PgDn>
                  b        scroll up, equivalent to <PgUp>
                  g        first line, equivalent to <Home>
                  G        last line, equivalent to <End>

          Z  :Change-Color-Mapping
              This key will take you to a separate screen where you can change the colors for the `current'
              window, or for all windows.  For details regarding this interactive  command  see  topic  4d.
              COLOR Mapping.

       *  The  commands  shown  with  an  asterisk (`*') are not available in Secure mode, nor will they be
          shown on the level-1 help screen.

### 4b. SUMMARY AREA Commands

The summary area interactive commands are always available  in  both  full-screen  mode  and  alter‐nate-display  mode. They affect the beginning lines of your display and will determine the position of messages and prompts.

These commands always impact just the 'current' window/field group.  See topic 5.  ALTERNATE-DISPLAY Provisions and the 'g' interactive command for insight into 'current' windows and field groups.

          C  :Show-scroll-coordinates toggle
              Toggle an informational message which is displayed whenever the message line is not otherwise
              being used.  For additional information see topic 5c. SCROLLING a Window.

          l  :Load-Average/Uptime toggle
              This is also the line containing the program name  (possibly  an  alias)  when  operating  in
              full-screen mode or the `current' window name when operating in alternate-display mode.

          t  :Task/Cpu-States toggle
              This  command  affects  from 2 to many summary area lines, depending on the state of the `1',
              `2' or `3' command toggles and whether or not top is running under true SMP.

              This portion of the summary area is also influenced by the `H' interactive command toggle, as
              reflected in the total label which shows either Tasks or Threads.

              This command serves as a 4-way toggle, cycling through these modes:
                  1. detailed percentages by category
                  2. abbreviated user/system and total % + bar graph
                  3. abbreviated user/system and total % + block graph
                  4. turn off task and cpu states display

              When  operating in either of the graphic modes, the display becomes much more meaningful when
              individual CPUs or NUMA nodes are also displayed.  See the the `1', `2' and `3' commands  be‐
              low for additional information.

          m  :Memory/Swap-Usage toggle
              This command affects the two summary area lines dealing with physical and virtual memory.

              This command serves as a 4-way toggle, cycling through these modes:
                  1. detailed percentages by memory type
                  2. abbreviated % used/total available + bar graph
                  3. abbreviated % used/total available + block graph
                  4. turn off memory display

          1  :Single/Separate-Cpu-States toggle
              This command affects how the `t' command's Cpu States portion is shown.  Although this toggle
              exists primarily to serve massively-parallel SMP machines, it is not restricted to solely SMP
              environments.

              When  you see `%Cpu(s):' in the summary area, the `1' toggle is On and all cpu information is
              gathered in a single line.  Otherwise, each cpu is displayed separately  as:  `%Cpu0,  %Cpu1,
              ...'  up to available screen height.

          2  :NUMA-Nodes/Cpu-Summary toggle
              This  command toggles between the `1' command cpu summary display (only) or a summary display
              plus the cpu usage statistics for each NUMA Node.  It is only available if a system  has  the
              requisite NUMA support.

          3  :Expand-NUMA-Node
              You  will  be invited to enter a number representing a NUMA Node.  Thereafter, a node summary
              plus the statistics for each cpu in that node will be shown until either the `1' or `2'  com‐
              mand  toggle is pressed.  This interactive command is only available if a system has the req‐
              uisite NUMA support.

       Note: If the entire summary area has been toggled Off for any window, you would be  left  with  just
       the message line.  In that way, you will have maximized available task rows but (temporarily) sacri‐
       ficed the program name in full-screen mode or the `current' window name  when  in  alternate-display
       mode.

### 4c. TASK AREA Commands
       
The task area interactive commands are always available in full-screen mode. The  task  area  interactive commands are never available in alternate-display mode if the 'current' window's task display has been toggled Off (see topic 5. ALTERNATE-DISPLAY Provisions).

       APPEARANCE of task window

          J  :Justify-Numeric-Columns toggle
              Alternates between right-justified (the default) and left-justified numeric data.  If the nu‐
              meric  data  completely fills the available column, this command toggle may impact the column
              header only.

          j  :Justify-Character-Columns toggle
              Alternates between left-justified (the default) and right-justified character data.   If  the
              character data completely fills the available column, this command toggle may impact the col‐
              umn header only.

         The following commands will also be influenced by the state of the global `B' (bold  enable)  tog‐
         gle.

          b  :Bold/Reverse toggle
              This  command  will impact how the `x' and `y' toggles are displayed.  It may also impact the
              summary area when a bar graph has been selected for cpu states or memory usage via the `t' or
              `m' toggles.

          x  :Column-Highlight toggle
              Changes  highlighting  for the current sort field.  If you forget which field is being sorted
              this command can serve as a quick visual reminder, providing the sort  field  is  being  dis‐
              played.  The sort field might not be visible because:
                  1) there is insufficient Screen Width
                  2) the `f' interactive command turned it Off

              Note: Whenever Searching and/or Other Filtering is active in a window, column highlighting is
              temporarily disabled.  See the notes at the end of topics 5d. SEARCHING and 5e. FILTERING for
              an explanation why.

          y  :Row-Highlight toggle
              Changes  highlighting  for "running" tasks.  For additional insight into this task state, see
              topic 3a. DESCRIPTIONS of Fields, the `S' field (Process Status).

              Use of this provision provides important insight into your system's health.  The  only  costs
              will be a few additional tty escape sequences.

          z  :Color/Monochrome toggle
              Switches  the  `current'  window  between  your  last used color scheme and the older form of
              black-on-white or white-on-black.  This command will alter both the  summary  area  and  task
              area but does not affect the state of the `x', `y' or `b' toggles.

       CONTENT of task window

          c  :Command-Line/Program-Name toggle
              This  command will be honored whether or not the COMMAND column is currently visible.  Later,
              should that field come into view, the change you applied will be seen.

          f | F  :Fields-Management
              These keys display a separate screen where you can change which fields are  displayed,  their
              order  and  also  designate  the sort field.  For additional information on these interactive
              commands see topic 3b. MANAGING Fields.

          o | O  :Other-Filtering
              You will be prompted for the selection criteria which then determines  which  tasks  will  be
              shown  in  the `current' window.  Your criteria can be made case sensitive or case can be ig‐
              nored.  And you determine if top should include or exclude matching tasks.

              See topic 5e. FILTERING in a window for details on these and additional  related  interactive
              commands.

          S  :Cumulative-Time-Mode toggle
              When  Cumulative  mode  is  On, each process is listed with the cpu time that it and its dead
              children have used.

              When Off, programs that fork into many separate tasks will appear less demanding.   For  pro‐
              grams like `init' or a shell this is appropriate but for others, like compilers, perhaps not.
              Experiment with two task windows sharing the same sort field but with  different  `S'  states
              and see which representation you prefer.

              After  issuing this command, you'll be informed of the new state of this toggle.  If you wish
              to know in advance whether or not Cumulative mode is in effect, simply ask for help and  view
              the window summary on the second line.

          u | U  :Show-Specific-User-Only
              You  will  be  prompted for the uid or name of the user to display.  The -u option matches on
              effective user whereas the -U option matches on any user (real, effective, saved, or filesys‐
              tem).

              Thereafter,  in  that task window only matching users will be shown, or possibly no processes
              will be shown.  Prepending an exclamation point (`!') to the user id or name instructs top to
              display only processes with users not matching the one provided.

              Different  task windows can be used to filter different users.  Later, if you wish to monitor
              all users again in the `current' window, re-issue this command but just press <Enter> at  the
              prompt.

          V  :Forest-View-Mode toggle
              In  this  mode, processes are reordered according to their parents and the layout of the COM‐
              MAND column resembles that of a tree.  In forest view mode it is still possible to toggle be‐
              tween  program  name  and command line (see the `c' interactive command) or between processes
              and threads (see the `H' interactive command).

              Note: Typing any key affecting the sort order will exit forest view  mode  in  the  `current'
              window.  See topic 4c. TASK AREA Commands, SORTING for information on those keys.

          v  :Hide/Show-Children toggle
              When in forest view mode, this key serves as a toggle to collapse or expand the children of a
              parent.

              The toggle is applied against the first (topmost) process in the `current' window.  See topic
              5c. SCROLLING a Window for additional information regarding vertical scrolling.

              If  the  target  process has not forked any children, this key has no effect.  It also has no
              effect when not in forest view mode.

       SIZE of task window

          i  :Idle-Process toggle
              Displays all tasks or just active tasks.  When this toggle is Off, tasks that have  not  used
              any  CPU since the last update will not be displayed.  However, due to the granularity of the
              %CPU and TIME+ fields, some processes may still be displayed that appear to have used no CPU.

              If this command is applied to the last task display when in alternate-display mode,  then  it
              will not affect the window's size, as all prior task displays will have already been painted.

          n | #  :Set-Maximum-Tasks
              You  will be prompted to enter the number of tasks to display.  The lessor of your number and
              available screen rows will be used.

              When used in alternate-display mode, this is the command that gives you precise control  over
              the  size  of each currently visible task display, except for the very last.  It will not af‐
              fect the last window's size, as all prior task displays will have already been painted.

              Note: If you wish to increase the size of the  last  visible  task  display  when  in  alter‐
              nate-display mode, simply decrease the size of the task display(s) above it.

       SORTING of task window

          For compatibility, this top supports most of the former top sort keys.  Since this is primarily a
          service to former top users, these commands do not appear on any help screen.
                command   sorted-field                  supported
                A         start time (non-display)      No
                M         %MEM                          Yes
                N         PID                           Yes
                P         %CPU                          Yes
                T         TIME+                         Yes

          Before using any of the following sort provisions, top suggests that you temporarily turn on col‐
          umn  highlighting  using the `x' interactive command.  That will help ensure that the actual sort
          environment matches your intent.

          The following interactive commands will only be honored when the current sort field  is  visible.
          The sort field might not be visible because:
                1) there is insufficient Screen Width
                2) the `f' interactive command turned it Off

             <  :Move-Sort-Field-Left
                 Moves  the  sort column to the left unless the current sort field is the first field being
                 displayed.

             >  :Move-Sort-Field-Right
                 Moves the sort column to the right unless the current sort field is the last  field  being
                 displayed.

          The  following  interactive commands will always be honored whether or not the current sort field
          is visible.

             f | F  :Fields-Management
                 These keys display a separate screen where you can change which field is used as the  sort
                 column,  among other functions.  This can be a convenient way to simply verify the current
                 sort field, when running top with column highlighting turned Off.

             R  :Reverse/Normal-Sort-Field toggle
                 Using this interactive command you  can  alternate  between  high-to-low  and  low-to-high
                 sorts.

          Note:  Field  sorting uses internal values, not those in column display.  Thus, the TTY and WCHAN
          fields will violate strict ASCII collating sequence.

### 4d. COLOR Mapping

When you issue the 'Z' interactive command, you will be presented with a separate screen. That screen  can  be used to change the colors in just the 'current' window or in all four windows before returning to the top display.

       The following interactive commands are available.
           4 upper case letters to select a target
           8 numbers to select a color
           normal toggles available
               B         :bold disable/enable
               b         :running tasks "bold"/reverse
               z         :color/mono
           other commands available
               a/w       :apply, then go to next/prior
               <Enter>   :apply and exit
               q         :abandon current changes and exit

       If you use `a' or `w' to cycle the targeted window, you will have applied the color scheme that  was
       displayed  when  you  left that window.  You can, of course, easily return to any window and reapply
       different colors or turn colors Off completely with the `z' toggle.

       The Color Mapping screen can also be used to change  the  `current'  window/field  group  in  either
       full-screen  mode  or alternate-display mode.  Whatever was targeted when `q' or <Enter> was pressed
       will be made current as you return to the top display.

## 5. ALTERNATE-DISPLAY Provisions
   
### 5a. WINDOWS Overview
  
Field Groups/Windows:
          
          In full-screen mode there is a single window represented by the entire screen.  That single  win‐
          dow  can  still be changed to display 1 of 4 different field groups (see the `g' interactive com‐
          mand, repeated below).  Each of the 4 field groups has a unique separately  configurable  summary
          area and its own configurable task area.

          In  alternate-display  mode,  those  4 underlying field groups can now be made visible simultane‐
          ously, or can be turned Off individually at your command.

          The summary area will always exist, even if it's only the message line.  At any given  time  only
          one summary area can be displayed.  However, depending on your commands, there could be from zero
          to four separate task displays currently showing on the screen.

Current Window:
          
          The `current' window is the window associated with the summary area and the window to which  task
          related  commands  are  always directed.  Since in alternate-display mode you can toggle the task
          display Off, some commands might be restricted for the `current' window.

          A further complication arises when you have toggled the first summary area line  Off.   With  the
          loss  of  the window name (the `l' toggled line), you'll not easily know what window is the `cur‐
          rent' window.

### 5b. COMMANDS for Windows

       - | _  :Show/Hide-Window(s) toggles
              The `-' key turns the `current' window's task display On and Off.  When On,  that  task  area
              will  show  a  minimum of the columns header you've established with the `f' interactive com‐
              mand.  It will also reflect any other task area options/toggles you've applied yielding  zero
              or more tasks.

              The  `_'  key  does  the same for all task displays.  In other words, it switches between the
              currently visible task display(s) and any task display(s) you had toggled Off.  If all 4 task
              displays  are  currently visible, this interactive command will leave the summary area as the
              only display element.

       *  = | +  :Equalize-(reinitialize)-Window(s)
              The `=' key forces the `current' window's task display to be visible.  It also  reverses  any
              active  `i'  (idle  tasks),  `n'  (max tasks), `u/U' (user filter), `o/O' (other filter), `v'
              (hide children) and 'L' (locate) commands.  Also, if the window had been scrolled, it will be
              reset with this command.  See topic 5c. SCROLLING a Window for additional information regard‐
              ing vertical and horizontal scrolling.

              The `+' key does the same for all windows.  The four task displays will reappear, evenly bal‐
              anced.   They  will  also have retained any customizations you had previously applied, except
              for the `i' (idle tasks), `n' (max tasks), `u/U' (user filter),  `o/O'  (other  filter),  `v'
              (hide children), `L' (locate) and scrolling interactive commands.

       *  A  :Alternate-Display-Mode toggle
              This command will switch between full-screen mode and alternate-display mode.

              The first time you issue this command, all four task displays will be shown.  Thereafter when
              you switch modes, you will see only the task display(s) you've chosen to make visible.

       *  a | w  :Next-Window-Forward/Backward
              This will change the `current' window, which in turn changes the window to which commands are
              directed.  These keys act in a circular fashion so you can reach any desired window using ei‐
              ther key.

              Assuming the window name is visible (you have not toggled `l' Off),  whenever  the  `current'
              window name loses its emphasis/color, that's a reminder the task display is Off and many com‐
              mands will be restricted.

       *  g  :Choose-Another-Window/Field-Group
              You will be prompted to enter a number between 1 and 4  designating  the  field  group  which
              should be made the `current' window.

              In  full-screen  mode,  this  command  is necessary to alter the `current' window.  In alter‐
              nate-display mode, it is simply a less convenient alternative to the `a' and `w' commands.

          G  :Change-Window/Field-Group-Name
              You will be prompted for a new name to be applied to the `current' window.  It does  not  re‐
              quire that the window name be visible (the `l' toggle to be On).

       *  The interactive commands shown with an asterisk (`*') have use beyond alternate-display mode.
              =, A, g    are always available
              a, w       act the same with color mapping
                         and fields management

### 5c. SCROLLING a Window
       
Typically a task window is a partial view into a systems's total tasks/threads which shows only some of the available fields/columns.  With these scrolling keys, you can move that  view  vertically  or horizontally to reveal any desired task or column.

       Up,PgUp  :Scroll-Tasks
           Move  the view up toward the first task row, until the first task is displayed at the top of the
           `current' window.  The Up arrow key moves a single line while PgUp scrolls the entire window.

       Down,PgDn  :Scroll-Tasks
           Move the view down toward the last task row, until the last task is the only task  displayed  at
           the  top of the `current' window.  The Down arrow key moves a single line while PgDn scrolls the
           entire window.

       Left,Right  :Scroll-Columns
           Move the view of displayable fields horizontally one column at a time.

           Note: As a reminder, some fields/columns are not fixed-width but allocated all remaining  screen
           width  when visible.  When scrolling right or left, that feature may produce some unexpected re‐
           sults initially.

           Additionally, there are special provisions for any variable width field when positioned  as  the
           last  displayed field.  Once that field is reached via the right arrow key, and is thus the only
           column shown, you can continue scrolling horizontally within such a field.  See the `C' interac‐
           tive command below for additional information.

       Home  :Jump-to-Home-Position
           Reposition the display to the un-scrolled coordinates.

       End  :Jump-to-End-Position
           Reposition  the display so that the rightmost column reflects the last displayable field and the
           bottom task row represents the last task.

           Note: From this position it is still possible to scroll down and right  using  the  arrow  keys.
           This is true until a single column and a single task is left as the only display element.

       C  :Show-scroll-coordinates toggle
           Toggle  an  informational  message which is displayed whenever the message line is not otherwise
           being used.  That message will take one of two forms depending on  whether  or  not  a  variable
           width column has also been scrolled.

             scroll coordinates: y = n/n (tasks), x = n/n (fields)
             scroll coordinates: y = n/n (tasks), x = n/n (fields) + nn

           The coordinates shown as n/n are relative to the upper left corner of the `current' window.  The
           additional `+ nn' represents the displacement into a variable width  column  when  it  has  been
           scrolled  horizontally.  Such displacement occurs in normal 8 character tab stop amounts via the
           right and left arrow keys.

           y = n/n (tasks)
               The first n represents the topmost visible task and is controlled by  scrolling  keys.   The
               second n is updated automatically to reflect total tasks.

           x = n/n (fields)
               The  first  n  represents the leftmost displayed column and is controlled by scrolling keys.
               The second n is the total number of displayable fields and is established with the  `f'  in‐
               teractive command.

       The  above  interactive commands are always available in full-screen mode but never available in al‐
       ternate-display mode if the `current' window's task display has been toggled Off.

       Note: When any form of filtering is active, you can expect some slight  aberrations  when  scrolling
       since  not  all  tasks  will be visible.  This is particularly apparent when using the Up/Down arrow
       keys.

### 5d. SEARCHING in a Window
       
You can use these interactive commands to locate a task row containing a particular value.

       L  :Locate-a-string
           You will be prompted for the case-sensitive string to locate starting from  the  current  window
           coordinates.  There are no restrictions on search string content.

           Searches  are  not limited to values from a single field or column.  All of the values displayed
           in a task row are allowed in a search string.  You may include spaces, numbers, symbols and even
           forest view artwork.

           Keying  <Enter>  with no input will effectively disable the `&' key until a new search string is
           entered.

       &  :Locate-next
           Assuming a search string has been established, top will attempt to locate the next occurrence.

       When a match is found, the current window is repositioned vertically so the task row containing that
       string  is  first.  The scroll coordinates message can provide confirmation of such vertical reposi‐
       tioning (see the `C' interactive command).  Horizontal scrolling,  however,  is  never  altered  via
       searching.

       The availability of a matching string will be influenced by the following factors.

          a. Which fields are displayable from the total available,
             see topic 3b. MANAGING Fields.

          b. Scrolling a window vertically and/or horizontally,
             see topic 5c. SCROLLING a Window.

          c. The state of the command/command-line toggle,
             see the `c' interactive command.

          d. The stability of the chosen sort column,
             for example PID is good but %CPU bad.

       If  a  search  fails,  restoring the `current' window home (unscrolled) position, scrolling horizon‐
       tally, displaying command-lines or choosing a more stable sort field could yet produce a  successful
       `&' search.

       The  above  interactive commands are always available in full-screen mode but never available in al‐
       ternate-display mode if the `current' window's task display has been toggled Off.

       Note: Whenever a Search is active in a window, top will turn  column  highlighting  Off  to  prevent
       false  matches  on internal non-display escape sequences.  Such highlighting will be restored when a
       window's search string is empty.  See the `x' interactive command for additional information on sort
       column highlighting.

### 5e. FILTERING in a Window

You can use this 'Other Filter' feature to establish selection criteria which will then determine which tasks are shown in the 'current' window.  Such filters can be made presistent if preserved  in the rcfile via the 'W' interactive command.

Establishing a filter requires: 1) a field name; 2) an operator; and 3) a selection value, as a minimum.  This is the most complex of top's user input requirements so, when you make a  mistake,  command recall will be your friend.  Remember the Up/Down arrow keys or their aliases when prompted for input.

       Filter Basics

          1. field names are case sensitive and spelled as in the header

          2. selection values need not comprise the full displayed field

          3. a selection is either case insensitive or sensitive to case

          4. the default is inclusion, prepending `!' denotes exclusions

          5. multiple selection criteria can be applied to a task window

          6. inclusion and exclusion criteria can be used simultaneously

          7. the 1 equality and 2 relational filters can be freely mixed

          8. separate unique filters are maintained for each task window

          If a field is not turned on or is not currently in view, then your selection  criteria  will  not
          affect  the  display.  Later, should a filtered field become visible, the selection criteria will
          then be applied.

       Keyboard Summary

         o  :Other-Filter (lower case)
             You will be prompted to establish a filter that ignores case when matching.

         O  :Other-Filter (upper case)
             You will be prompted to establish a case sensitive filter.

        ^O  :Show-Active-Filters (Ctrl key + `o')
             This can serve as a reminder of which filters are active in the `current' window.   A  summary
             will be shown on the message line until you press the <Enter> key.

         =  :Reset-Filtering in current window
             This  clears  all  of your selection criteria in the `current' window.  It also has additional
             impact so please see topic 4a. GLOBAL Commands.

         +  :Reset-Filtering in all windows
             This clears the selection criteria in all windows, assuming you are in alternate-display mode.
             As  with  the `=' interactive command, it too has additional consequences so you might wish to
             see topic 5b. COMMANDS for Windows.

       Input Requirements

          When prompted for selection criteria, the data you provide must take one of two forms.  There are
          3  required pieces of information, with a 4th as optional.  These examples use spaces for clarity
          but your input generally would not.
                  #1           #2  #3              ( required )
                  Field-Name   ?   include-if-value
               !  Field-Name   ?   exclude-if-value
               #4                                  ( optional )

          Items #1, #3 and #4 should be self-explanatory.  Item #2 represents both a required delimiter and
          the operator which must be one of either equality (`=') or relation (`<' or `>').

          The `=' equality operator requires only a partial match and that can reduce your `if-value' input
          requirements.  The `>' or `<' relational operators always employ string  comparisons,  even  with
          numeric  fields.  They are designed to work with a field's default justification and with homoge‐
          neous data.  When some field's numeric amounts have been subjected to scaling while  others  have
          not, that data is no longer homogeneous.

          If you establish a relational filter and you have changed the default Numeric or Character justi‐
          fication, that filter is likely to fail.  When a relational filter is applied to a  memory  field
          and you have not changed the scaling, it may produce misleading results.  This happens, for exam‐
          ple, because `100.0m' (MiB) would appear greater than `1.000g' (GiB) when compared as strings.

          If your filtered results appear suspect, simply altering justification or scaling may yet achieve
          the desired objective.  See the `j', `J' and `e' interactive commands for additional information.

       Potential Problems

          These GROUP filters could produce the exact same results or the second one might not display any‐
          thing at all, just a blank task window.
               GROUP=root        ( only the same results when )
               GROUP=ROOT        ( invoked via lower case `o' )

          Either of these RES filters might yield inconsistent and/or misleading results, depending on  the
          current memory scaling factor.  Or both filters could produce the exact same results.
               RES>9999          ( only the same results when )
               !RES<10000        ( memory scaling is at `KiB' )

          This nMin filter illustrates a problem unique to scalable fields.  This particular field can dis‐
          play a maximum of 4 digits, beyond which values are automatically scaled to  KiB  or  above.   So
          while amounts greater than 9999 exist, they will appear as 2.6m, 197k, etc.
               nMin>9999         ( always a blank task window )

       Potential Solutions

          These examples illustrate how Other Filtering can be creatively applied to achieve almost any de‐
          sired result.  Single quotes are sometimes shown to delimit the spaces which are part of a filter
          or  to  represent  a  request for status (^O) accurately.  But if you used them with if-values in
          real life, no matches would be found.

          Assuming field nTH is displayed, the first filter will result in  only  multi-threaded  processes
          being  shown.   It  also  reminds us that a trailing space is part of every displayed field.  The
          second filter achieves the exact same results with less typing.
               !nTH=` 1 '                ( ' for clarity only )
               nTH>1                     ( same with less i/p )

          With Forest View mode active and the COMMAND column in view, this  filter  effectively  collapses
          child processes so that just 3 levels are shown.
               !COMMAND=`       `- '     ( ' for clarity only )

          The  final  two  filters  appear as in response to the status request key (^O).  In reality, each
          filter would have required separate input.  The PR example shows the two concurrent filters  nec‐
          essary to display tasks with priorities of 20 or more, since some might be negative.  Then by ex‐
          ploiting trailing spaces, the nMin series of filters could achieve the  failed  `9999'  objective
          discussed above.
               `PR>20' + `!PR=-'         ( 2 for right result )
               `!nMin=0 ' + `!nMin=1 ' + `!nMin=2 ' + `!nMin=3 ' ...

       Note:  Whenever Other Filtering is active in a window, top will turn column highlighting Off to pre‐
       vent false matches on internal non-display escape sequences.  Such  highlighting  will  be  restored
       when a window is no longer subject to filtering.  See the `x' interactive command for additional in‐
       formation on sort column highlighting.
