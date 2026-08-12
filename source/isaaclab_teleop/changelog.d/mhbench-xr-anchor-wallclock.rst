Fixed
^^^^^

* Fixed rotation smoothing in :class:`~isaaclab_teleop.xr_anchor_utils.XrAnchorSynchronizer`
  for ``FOLLOW_PRIM_SMOOTHED`` mode to derive its slerp fraction from the
  wall-clock time between frames, as
  :attr:`~isaaclab_teleop.xr_cfg.XrCfg.anchor_rotation_smoothing_time` documents,
  instead of the fixed rendering step size with a 0.05 floor -- which pinned the
  smoother to a ~19.5-frame time constant, so the view anchor lagged a turning
  robot by ~1.7 s whenever the application ran at 11 Hz.
