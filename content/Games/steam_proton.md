## > WINED3D instead of Vulcan (Required for Wine 5.0+ / Radeon 5450)
- Library > Right click game > Properties
    - SET LAUNCH OPTIONS
        - PROTON_USE_WINED3D=1 %command%

## > Vulcan
- Library > Right click game > Properties
    - SET LAUNCH OPTIONS
        - +r_renderapi 1

## > Debug
- SET LAUNCH OPTIONS
    - DEBUGGER=gdb steam
- Library > Right click game > Properties
    - SET LAUNCH OPTIONS
        - -con_logfile
